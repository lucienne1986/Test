 
                      
        # AMM12
        ___
        
        [Purpose](#purpose)  |  [Contact](#contact)  |  [License](#license)  |  [Configuration](#configuration) |
          [Input Files](#input-files)  |  [Diagnostics](#diagnostics)  |
          [Installation](#installation) |  [Static Page](#/AMM12)
        
        ____
        
        # Purpose
        
        The purpose of this is to create a readme file
        
        
        # Contact
        
        Lucienne Micallef - lmicallef@geomar.de
        
        
        # License
        
        **By downloading this repository and using this code you agree 
        to the following conditions.**
        
        The code in this project is based on the [NEMO](http://www.nemo-ocean.eu) 
        software (Copyright (c) Centre National de la Recherche Scientifique CNRS).
        
        The original code as well as the contribution to this code in this project are 
        licensed under the conditions of [CeCILL](http://www.cecill.info). 
        
        The person stated under '*Contact*' above is the owner of the intellectual 
        property rights of these contributions and **must be informed afore** publishing
        and **must be cited** in every published work that is based completely or 
        partially on the modifications and additional code provided by this configuration.
        
        Usage is at one's own risk. 
        
        
        # Configuration
        
|  Characteristic | Specs |
|-------------- | -------------- | 
| **NEMOGCM repository** | git@git.geomar.de:NEMO/NEMOGCM.git | 
| **Git Branch** | release-3.6.3.x | 
| **Nemo-ocean repository** | http://forge.ipsl.jussieu.fr/nemo/svn/branches/2015/nemo_v3_6_STABLE/NEMOGCM | 
| **Nemo-ocean revision** | 556 | 
| **Components** | AMM12 | 
| **Reference Configuration** |  -  | 
| **CPP keys** | cpp_AMM12.fcm | 
| **Grid** | "amm", sco (s- or hybrid z-s-coordinate) | 
| **Resolution** | 11.0 | 
| **Horizontal Gridpoints** | 198.0 x 224.0 | 
| **Vertical Levels** | 51.0 | 
| **Atmospheric Condition** | Flux formulation + Freshwater Budget Correction (Mode 0) | 
| **Time Step [s]** | 600 | 
| **Passive Tracers** | Unknown | 
| **Number of Nests** | 0 | 


        
        
        The default experiment settings can be found in the [EXP00](EXP00) folder.
        The modified code is located in the [MY_SRC](MY_SRC) directory.
        
               
        # Input Files
        
        *  **NEMO Input File:** File names as they are expected by NEMO  
        *  **Reference:** Citation for an article or report, webpage or even better: DOI  
        *  **Download:** Link for direct downloading the file (no user-interaction preferred to make it script-compliant)  
        
        The actual file names should follow the *Guidelines for Naming DRAKKAR Input 
        File Names*: "\`NemoName\`\_\`NemoVersion\`\_\`ConfigGrid\`\_\`Version\`.nc"
        
        
|  **NEMO Input File** | **Reference (DOI)** | **Download** |
|-------------- | -------------- | -------------- | 
| coordinates.nc | --- | git@git.geomar.de:ORCA/025-data/coordinates.git/coordinates__3.6.0_ORCA025_Kv1.0.1.nc | 
| bathy_meter.nc | --- | git@git.geomar.de:ORCA/025-data/bathy_meter.git/bathy_meter__3.6.0_ORCA025.L46_Kv1.0.1.nc | 
| bfr_coef.nc | --- | git@git.geomar.de:ORCA/025-data/bfr_coef.git/bfr_coef__3.6.0_ORCA025_Kv1.0.1.nc | 
| data_tem.nc | --- | git@git.geomar.de:ORCA/025-data/ocean-init/PHC-2.1_WOA98.git/Tpot_PHC2.1_WOA98__3.6.0_ORCA025.L46_Kv1.0.0.nc | 
| data_sal.nc | --- | git@git.geomar.de:ORCA/025-data/ocean-init/PHC-2.1_WOA98.git/Salt_PHC2.1_WOA98__3.6.0_ORCA025.L46_Kv1.0.0.nc | 
| subbasins.nc | --- | git@git.geomar.de:ORCA/025-data/subbasins.git/subbasins__3.6.0_ORCA025_Kv1.0.1.nc | 
| Ice_initialization.nc | --- | http://thredds.geomar.de/thredds/fileServer/orca-I/ORCA025-I/misc/Ice_initialization_ORCS025.L46-K3469_30.nc | 
| runoff_1m_nomask.nc | --- | git@git.geomar.de:ORCA/025-data/runoff_12month.git/runoff_12month__3.6.0_ORCA025_Kv1.0.1.nc | 
| reshape_core_orca025_bilin.nc | --- | git@git.geomar.de:ORCA/025-data/reshape_core.git/reshape_core_bilin__3.6.0_ORCA025_Kv1.0.1.nc | 
| reshape_core_orca025_bicub.nc | --- | git@git.geomar.de:ORCA/025-data/reshape_core.git/reshape_core_bicub__3.6.0_ORCA025_Kv1.0.1.nc | 
| Levitus_p2.1.1-12_sss__correc_FUS_orca025_wozax.nc | --- | http://thredds.geomar.de/thredds/fileServer/orca-I/ORCA025-I/misc/Levitus_p2.1.1-12_sss__correc_FUS_orca025_wozax.nc | 
| dmpmsk_MedSea_orca025.l46_RA.nc | --- | http://thredds.geomar.de/thredds/fileServer/orca-I/ORCA025-I/misc/dmpmsk_MedSea_orca025.l46_RA.nc | 


        
        # Diagnostics
        
        See [DIAG](DIAG) for some standard diagnostics from a simulation with this configuraton.
        
        # Installation
        
        There are plenty of ways how to install a local copy of this configuration:
        
        1. You can [clone it with git](#install-with-git) (regardless of whether your NEMOGCM path is already 
           under git control or not). 
        2. Or you just download an archive from the web interface.  
        
        In some cases there are different versions of the same configuration 
        in separate branches (e.g. to reflect different NEMO revisions); **check the branches/tags** 
        menu on the web interface or use the git branch and checkout commands to select 
        the version you're interested in.
        
        <!--For further details, please read the [HELP pages](https://gitlab.com/DRAKKARshare/help/edit/master/GetConfiguration.md).-->
        
        
        ## Install with \`git\`
        
        **{- IMPORTANT: -}** The following guidelines assume, that you're already registered at 
        https://git.geomar.de and your public SSH key has been deposited under your gitlab profile.
        
        
        
        #### (A) NEMOGCM already under git control
        
        If your **NEMOGCM installation is already under git control** you cannot clone a 
        different repository into the existing working copy. 
        Instead, you can use \`git subtree\` to inject files from another remote repository 
        into a particular sub-folder of your existing working tree.
        
        Within NEMOGCM directory:
        
        **OPTION 1 - With ngit**
        
        ~~~
        cd NEMOGCM/CONFIG
        ngit gr git@git.geomar.de:NEMO/EXP/AMM12.git -b release-3.6.3.x:-master
        ~~~
        
        >>>
        **COMMAND:** \`ngit gr <Repo> [<LocalName>] [-b <Branch>]\`  
        
         * **&lt;Repo>**: git@*.git repository url for the chosen reference configuration
         * **&lt;LocalName>**: Optional name of the folder the reference-configuration is donwloaded to. Default is the Repository's name
         * **-b &lt;Branch>**: Optional name of the branch to download. Default is the name of the current branch of NEMOGCM or master if not existend.
        >>>
        
        
        
        **Option 2 - With git commands**
        
        ~~~bash
        cd NEMOGCM
        git remote add -f remote_AMM12 git@git.geomar.de:NEMO/EXP/AMM12.git   # add remote
        git subtree add --prefix CONFIG/AMM12 remote_AMM12 release-3.6.3.x:-master --squash     # donwload master branch into sub-folder
        cd CONFIG/AMM12 remote_AMM12
        cat cfg.txt >> ../cfg.txt
        ~~~
        
        > In this case, you keep the information from where you have downloaded the reference configuration (see \`git remote -v\`).
        
        Or even shorter, without keeping remote source information (not recommended):
        
        ~~~bash
        cd NEMOGCM
        git subtree add --prefix CONFIG/AMM12 git@git.geomar.de:NEMO/EXP/AMM12.git release-3.6.3.x:-master --squash
        cd CONFIG/AMM12 remote_AMM12
        cat cfg.txt >> ../cfg.txt
        ~~~
        
        
        #### (B) NEMOGCM not under git control
        
        If your NEMOGCM installation **is not under git control already**, you can clone this configuration using the URL specified on the project's front page:
        
        ~~~bash
        cd NEMOGCM/CONFIG  
        git clone git@git.geomar.de:NEMO/EXP/AMM12.git
        cat AMM12/cfg.txt >> cfg.txt
        ~~~
        
        This wil create a new configuration folder, which can be used as a reference case for \`makenemo -r\`. 
        Make sure, you add this confiuration  to the local registry file \`cfg.txt\` before invoking \`makenemo\`.
        
        
        #### Other revisions
        
        The revision that will be installed, is the most recent one from the **master** branch. 
        If you're seeking another branch/revision of this configuration (e.g. an older one), 
        you can browse available branches/tags via the web-interface or list alternative 
        branches on the command line and swap available branches/tags easily with \`checkout\`:
        
        ~~~bash
        cd AMM12
        git branches -r
        git checkout otherBranch
        ~~~
        
        Note: *origin/HEAD* in the output listing is not a branch in its own but points to the 
        default branch (master branch in most cases).
        
        
        
