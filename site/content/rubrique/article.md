---
title: "Angular"
date: 2018-11-26T20:45:49+01:00
draft: true
---


### Npm install

Quand `npm install` fonctionne pas a cause du composant _Visual C++ "VCBuild.exe"_,
il suffit de faire :

* `npm install --global --production windows-build-tools`
* `npm update`


### Desactiver la sécurité chrome

Chrome dev : `--disable-features=CrossSiteDocumentBlockingIfIsolating`

### Ng

Si ng ne fonctionne pas ou n'est pas trouvé : `npm install -g @angular/cli`

### Jenkins

Sur la plateforme il faut d'abord installer l'environnement

 * Ajouter le dépot `sudo yum install epel-release`
 * Télécharger `curl --silent --location https://rpm.nodesource.com/setup_9.x | sudo bash -`
 * Installer `sudo yum install -y nodejs` et `sudo yum install -y gcc-c++ make`
 * Installer bzip2 sinon rien ne marche : `sudo yum install bzip2`

Configurer npm ?

* npmrc vim `/usr/etc/npmrc`
* y ajouter `phantomjs_cdnurl=https://bitbucket.org/ariya/phantomjs/downloads`