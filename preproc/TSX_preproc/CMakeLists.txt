#
#	$Id: $
#

if (HAVE_M_LIBRARY)
	# link the math library
	set (LINK_LIBS m)
endif (HAVE_M_LIBRARY)

include_directories (include ../../gmtsar ../S1A_preproc/include ${GMT_INCLUDE_DIR})

set (LINK_LIBS ${LINK_LIBS} gmtsar xmlC)

add_executable (make_slc_tsx src/make_slc_tsx.c)
target_link_libraries (make_slc_tsx ${LINK_LIBS})


# add the install targets
install (TARGETS make_slc_tsx
	ARCHIVE DESTINATION lib
	COMPONENT Runtime
	LIBRARY DESTINATION lib
	COMPONENT Runtime
	RUNTIME DESTINATION bin
	COMPONENT Runtime)

# vim: textwidth=78 noexpandtab tabstop=2 softtabstop=2 shiftwidth=2
