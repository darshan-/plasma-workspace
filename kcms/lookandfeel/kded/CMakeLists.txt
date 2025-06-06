kcoreaddons_add_plugin(autodarklightlnf INSTALL_NAMESPACE "kf6/kded")

target_sources(autodarklightlnf PRIVATE
    idletimeout.cpp
    lookandfeelautoswitcher.cpp
)

kconfig_target_kcfg_file(autodarklightlnf
    FILE ${CMAKE_CURRENT_SOURCE_DIR}/../lookandfeelsettings.kcfg
    CLASS_NAME LookAndFeelSettings
)

kconfig_target_kcfg_file(autodarklightlnf
    FILE lookandfeelautoswitcherstate.kcfg
    CLASS_NAME LookAndFeelAutoSwitcherState
    MUTATORS
)

target_link_libraries(autodarklightlnf PRIVATE
    Qt6::Core
    KF6::ConfigCore
    KF6::ConfigGui
    KF6::CoreAddons
    KF6::DBusAddons
    KF6::IdleTime
    KNightTime
)
