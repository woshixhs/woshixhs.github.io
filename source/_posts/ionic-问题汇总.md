title: "ionic 问题汇总"
date: 2015-04-19 20:50:35
categories: ionic
tags:

----------
#####**Error: spawn EACCES** 
	Error: spawn EACCES
    at exports._errnoException (util.js:746:11)
    at ChildProcess.spawn (child_process.js:1162:11)
    at Object.exports.spawn (child_process.js:995:9)
    at Object.exports.spawn (/usr/local/lib/node_modules/cordova/node_modules/cordova-lib/src/cordova/superspawn.js:100:31)
    at runScriptViaChildProcessSpawn (/usr/local/lib/node_modules/cordova/node_modules/cordova-lib/src/hooks/HooksRunner.js:188:23)
    at runScript (/usr/local/lib/node_modules/cordova/node_modules/cordova-lib/src/hooks/HooksRunner.js:131:16)
    at /usr/local/lib/node_modules/cordova/node_modules/cordova-lib/src/hooks/HooksRunner.js:114:20
    at _fulfilled (/usr/local/lib/node_modules/cordova/node_modules/cordova-lib/node_modules/q/q.js:787:54)
    at self.promiseDispatch.done (/usr/local/lib/node_modules/cordova/node_modules/cordova-lib/node_modules/q/q.js:816:30)
    at Promise.promise.promiseDispatch (/usr/local/lib/node_modules/cordova/node_modules/cordova-lib/node_modules/q/q.js:749:13)
    解决方案: 先执行命令
    ionic hooks add
[参考](http://forum.ionicframework.com/t/how-to-fix-this-error-spawn-eacces/20490)
#####**Error: EACCES, permission denied** 
	Error: EACCES, permission denied '/home/kim/work/web_html5_app/sidemunuDemo/platforms/android/assets/www/cordova_plugins.js'
    at Error (native)
    at Object.fs.openSync (fs.js:500:18)
    at Object.fs.writeFileSync (fs.js:1099:15)
    at Object.handlePrepare (/usr/local/lib/node_modules/cordova/node_modules/cordova-lib/src/plugman/prepare.js:155:8)
    at /usr/local/lib/node_modules/cordova/node_modules/cordova-lib/src/cordova/prepare.js:108:21
    at Array.map (native)
    at /usr/local/lib/node_modules/cordova/node_modules/cordova-lib/src/cordova/prepare.js:73:40
    at _fulfilled (/usr/local/lib/node_modules/cordova/node_modules/cordova-lib/node_modules/q/q.js:787:54)
    at self.promiseDispatch.done (/usr/local/lib/node_modules/cordova/node_modules/cordova-lib/node_modules/q/q.js:816:30)
    at Promise.promise.promiseDispatch (/usr/local/lib/node_modules/cordova/node_modules/cordova-lib/node_modules/q/q.js:749:13)
    解决方案:执行以下命令
    sudo chmod -R a+rwx /appfolder
   [参考](http://forum.ionicframework.com/t/how-to-fix-this-error-spawn-eacces/20490)

