
include_directories( ${KHTML_SOURCE_DIR}
                     ${KHTML_BINARY_DIR}
)
include_directories(${ZLIB_INCLUDE_DIR})

########### next target ###############

set(kmultipart_PART_SRCS kmultipart.cpp httpfiltergzip.cpp)
add_library(kmultipart MODULE ${kmultipart_PART_SRCS})

target_link_libraries(kmultipart
                        ${ZLIB_LIBRARY}
                        KF5::Parts
                        KF5::Archive
                        KF5::WidgetsAddons
                        KF5::XmlGui
                        KF5::I18n
                        KF5::TextWidgets)

install(TARGETS kmultipart  DESTINATION ${KDE_INSTALL_PLUGINDIR}/kf5/parts)
install(FILES kmultipart.desktop  DESTINATION  ${KDE_INSTALL_KSERVICES5DIR} )




