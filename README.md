___

[Purpose](#purpose)  |  [Contact](#contact)  |  [License](#license)  |  [Configuration](#configuration) |
  [Input Files](#input-files)  |  [Diagnostics](#diagnostics)  |
  [Installation](#installation) ${zPAGE}

____


# Purpose

#{_PURPOSE_}


# Contact

${_CONTACT_}


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


|  **Characteristic**  |  **Specs** |   
|---|---|---
|**NEMOGCM$nbsp;repository**     | _CURREPO_  |   
| **Git Branch**  |_NEMOBRANCH_   |   
|**nemo-ocean repository**    | _NEMOREPO_  | 
|**nemo-ocean revision**     | _NEMOREVISION_  |   
|**Components**  |_COMPONENTS_   |   
|**Reference Configuration**    |[${_REFCONFIG_##*/}](${_REFCONFIG_})  | 
|**CPP keys**     | _CPPKEYS_  |   
|**Grid**  |${_HGRIDTYPE_}, ${_VGRIDTYPE_}   |   
|**Resolution**     | ${_RESOLUTION_}  | 
|**Horizontal Gridpoints**    |${_HGRIDPT_} | 
|**Vertical Levels**     | ${_VGRIDPTZ_}  |   
|**Atmospheric Condition**   |${_ATMOS_}   |   
|**Time Step [s]**    | ${_OCEANRDT_}  |
|**Passive Tracers**   |${_PASSIVTRACERS_}   |   
|**Number of Nests**    | ${_NESTNUMBER_}  | 


The default experiment settings can be found in the [EXP00](EXP00) folder.
The modified code is located in the [MY_SRC](MY_SRC) directory.

# Input Files

*  **NEMO Input File:** File names as they are expected by NEMO  
*  **Reference:** Citation for an article or report, webpage or even better: DOI  
*  **Download:** Link for direct donwloading the file (no user-interaction preferred to make it script-compliant)  

The actual file names should follow the *Guidelines for Naming DRAKKAR Input 
File Names*: "\`NemoName\`\\_\`NemoVersion\`\\_\`ConfigGrid\`\\_\`Version\`.nc"

$(list_inputfiles)


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
https://${zGITSERVER} and your public SSH key has been deposited under your gitlab profile.



#### (A) NEMOGCM already under git control

If your **NEMOGCM installation is already under git control** you cannot clone a 
different repository into the existing working copy. 
Instead, you can use \`git subtree\` to inject files from another remote repository 
into a particular sub-folder of your existing working tree.

Within NEMOGCM directory:

**OPTION 1 - With ngit**

~~~
cd NEMOGCM/CONFIG
ngit gr git@${zGITSERVER}:${zGITNMSPC}/${_CONFNAME_}.git -b ${_NEMOBRANCH_:-master}
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
git remote add -f remote_${_CONFNAME_} git@${zGITSERVER}:${zGITNMSPC}/${_CONFNAME_}.git   # add remote
git subtree add --prefix CONFIG/${_CONFNAME_} remote_${_CONFNAME_} ${_NEMOBRANCH_:-master} --squash     # donwload master branch into sub-folder
cd CONFIG/${_CONFNAME_} remote_${_CONFNAME_}
cat cfg.txt >> ../cfg.txt
~~~

> In this case, you keep the information from where you have downloaded the reference configuration (see \`git remote -v\`).


Or even shorter, without keeping remote source information (not recommended):

~~~bash
cd NEMOGCM
git subtree add --prefix CONFIG/${_CONFNAME_} git@${zGITSERVER}:${zGITNMSPC}/${_CONFNAME_}.git ${_NEMOBRANCH_:-master} --squash
cd CONFIG/${_CONFNAME_} remote_${_CONFNAME_}
cat cfg.txt >> ../cfg.txt
~~~

#### (B) NEMOGCM not under git control

If your NEMOGCM installation **is not under git control already**, you can clone this configuration using the URL specified on the project's front page:

~~~bash
cd NEMOGCM/CONFIG  
git clone git@${zGITSERVER}:${zGITNMSPC}/${_CONFNAME_}.git
cat ${_CONFNAME_}/cfg.txt >> cfg.txt
~~~

This wil create a new configuration folder, which can be used as a reference case for \`makenemo -r\`. 
Make sure, you add this confiuration  to the local registry file \`cfg.txt\` before invoking \`makenemo\`.


#### Other revisions

The reversion that will be installed, is the most recent one from the **master** branch. 
If you're seeking another branch/reversion of this configuration (e.g. an older one), 
you can browse available branches/tags via the web-interface or list alternative 
branches on the command line and swap available branches/tags easily with \`checkout\`:

~~~bash
cd ${_CONFNAME_}
git branches -r
git checkout otherBranch
~~~

Note: *origin/HEAD* in the output listing is not a branch in its own but points to the 
default branch (master branch in most cases).
        
