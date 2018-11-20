# Windows 10 Optimization And Configurations
 - Applies all types of settings for Windows 10. Script variables can be set either internal (standalone) or using MDT/SCCM Task sequence custom properties. Ultimately MDT/SCCM properties will overwrite internal variable if set. 

## Options not working (yet)
** Reason: the goal is to set any registry settings within local gpo instead of hard coding the registry **
 - CFG_UseLGPOForConfigs=True 
 - LGPOPath=%DeployRoot%\Scripts\Custom\OS-Configs\Tools\LGPO
 
## Add to MDT CustomSettings.ini
    Properties=CFG_UseLGPOForConfigs,LGPOPath,CFG_SetPowerCFG,CFG_PowerCFGFilePath,CFG_EnableVerboseMsg,CFG_EnablePSLogging,CFG_ApplySTIGItems,CFG_DisableAutoRun,CFG_CleanSampleFolders,CFG_DisableCortana,CFG_DisableInternetSearch,CFG_EnableVDIOptimizations,CFG_EnableOfficeOneNote,CFG_EnableRDP,CFG_DisableOneDrive,CFG_PreferIPv4OverIPv6,CFG_RemoveActiveSetupComponents,CFG_DisableWindowsFirstLoginAnimation,CFG_DisableIEFirstRunWizard,CFG_DisableWMPFirstRunWizard,CFG_DisableEdgeIconCreation,CFG_DisableNewNetworkDialog,CFG_DisableInternetServices,CFG_DisabledUnusedServices,CFG_DisabledUnusedFeatures,CFG_DisableSchTasks,CFG_DisableDefender,CFG_DisableFirewall,CFG_DisableWireless,CFG_DisableBluetooth,CFG_EnableRemoteRegistry,CFG_DisableFirewall,CFG_ApplyPrivacyMitigations,CFG_EnableCredGuard,CFG_InstallLogonScript,CFG_LogonScriptPath,CFG_EnableWinRM,CFG_EnableAppsRunAsAdmin,CFG_DisableUAC,CFG_DisableWUP2P,CFG_EnableIEEnterpriseMode,CFG_IEEMSiteListPath,CFG_PreCompileAssemblies,CFG_DisableIndexing


'// Configuration Settings (Win10OptimizeAndConfig.ps1)
    CFG_UseLGPOForConfigs=True
    CFG_SetPowerCFG=[Custom|High Performance|Balanced]
    CFG_PowerCFGFilePath=%DeployRoot%\Scripts\Custom\OS-Configs\AlwaysOnPowerScheme.pow
    CFG_ApplySTIGItems=True
    CFG_EnableVerboseMsg=True
    CFG_EnablePSLogging=True
    CFG_DisableAutoRun=True
    CFG_CleanSampleFolders=True
    CFG_DisableCortana=True
    CFG_DisableInternetSearch=True
    CFG_EnableVDIOptimizations=True
    CFG_EnableOfficeOneNote=True
    CFG_EnableRDP=True
    CFG_DisableOneDrive=True
    CFG_PreferIPv4OverIPv6=True
    CFG_RemoveActiveSetupComponents=True
    CFG_DisableWindowsFirstLoginAnimation=True
    CFG_DisableIEFirstRunWizard=True
    CFG_DisableWMPFirstRunWizard=True
    CFG_DisableEdgeIconCreation=True
    CFG_DisableNewNetworkDialog=True
    CFG_DisableInternetServices=True
    CFG_DisabledUnusedServices=True
    CFG_DisabledUnusedFeatures=True
    CFG_DisableSchTasks=True
    CFG_DisableDefender=False
    CFG_DisableFirewall=False
    CFG_DisableWireless=True
    CFG_DisableBluetooth=True
    CFG_EnableRemoteRegistry=True
    CFG_DisableFirewall=False
    CFG_ApplyPrivacyMitigations=True
    CFG_InstallLogonScript=False
    CFG_LogonScriptPath=''
    CFG_EnableWinRM=True
    CFG_EnableAppsRunAsAdmin=False
    CFG_DisableUAC=False
    CFG_DisableWUP2P=True
    CFG_EnableIEEnterpriseMode=False
    CFG_IEEMSiteListPath=\\%JoinDomain%\NETLOGON\IE_EM_List\SiteList.xml
    CFG_PreCompileAssemblies=True
    CFG_DisableIndexing=True

'// Path to LGPO.exe
LGPOPath=%DeployRoot%\Scripts\Custom\OS-Configs\Tools\LGPO

