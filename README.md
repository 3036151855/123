!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <meta name="keywords" content="CPS, CPS测试, 手速, 点击速度测试, 鼠标点击速度"/>
    <meta name="description" content="在线CPS测试。在测试区域内，尽可能的在十秒内快速点击鼠标,你将获得平均的CPS。"/>
    <link rel="shortcut icon" href="https://i.loli.net/2019/08/27/1H48VWXfsTmoaZ7.png" />
    <link rel="stylesheet" href="https://at.alicdn.com/t/font_1443928_pzbat0x9z2i.css">
    <script src="https://ajax.aspnetcdn.com/ajax/jQuery/jquery-3.4.1.js"></script>
    <script>
        ;(function(){'use strict';function FastClick(layer,options){var oldOnClick;options=options||{};this.trackingClick=false;this.trackingClickStart=0;this.targetElement=null;this.touchStartX=0;this.touchStartY=0;this.lastTouchIdentifier=0;this.touchBoundary=options.touchBoundary||10;this.layer=layer;this.tapDelay=options.tapDelay||200;this.tapTimeout=options.tapTimeout||700;if(FastClick.notNeeded(layer)){return}function bind(method,context){return function(){return method.apply(context,arguments)}}var methods=['onMouse','onClick','onTouchStart','onTouchMove','onTouchEnd','onTouchCancel'];var context=this;for(var i=0,l=methods.length;i<l;i++){context[methods[i]]=bind(context[methods[i]],context)}if(deviceIsAndroid){layer.addEventListener('mouseover',this.onMouse,true);layer.addEventListener('mousedown',this.onMouse,true);layer.addEventListener('mouseup',this.onMouse,true)}layer.addEventListener('click',this.onClick,true);layer.addEventListener('touchstart',this.onTouchStart,false);layer.addEventListener('touchmove',this.onTouchMove,false);layer.addEventListener('touchend',this.onTouchEnd,false);layer.addEventListener('touchcancel',this.onTouchCancel,false);if(!Event.prototype.stopImmediatePropagation){layer.removeEventListener=function(type,callback,capture){var rmv=Node.prototype.removeEventListener;if(type==='click'){rmv.call(layer,type,callback.hijacked||callback,capture)}else{rmv.call(layer,type,callback,capture)}};layer.addEventListener=function(type,callback,capture){var adv=Node.prototype.addEventListener;if(type==='click'){adv.call(layer,type,callback.hijacked||(callback.hijacked=function(event){if(!event.propagationStopped){callback(event)}}),capture)}else{adv.call(layer,type,callback,capture)}}}if(typeof layer.onclick==='function'){oldOnClick=layer.onclick;layer.addEventListener('click',function(event){oldOnClick(event)},false);layer.onclick=null}}var deviceIsWindowsPhone=navigator.userAgent.indexOf("Windows Phone")>=0;var deviceIsAndroid=navigator.userAgent.indexOf('Android')>0&&!deviceIsWindowsPhone;var deviceIsIOS=/iP(ad|hone|od)/.test(navigator.userAgent)&&!deviceIsWindowsPhone;var deviceIsIOS4=deviceIsIOS&&(/OS 4_\d(_\d)?/).test(navigator.userAgent);var deviceIsIOSWithBadTarget=deviceIsIOS&&(/OS [6-7]_\d/).test(navigator.userAgent);var deviceIsBlackBerry10=navigator.userAgent.indexOf('BB10')>0;FastClick.prototype.needsClick=function(target){switch(target.nodeName.toLowerCase()){case'button':case'select':case'textarea':if(target.disabled){return true}break;case'input':if((deviceIsIOS&&target.type==='file')||target.disabled){return true}break;case'label':case'iframe':case'video':return true}return(/\bneedsclick\b/).test(target.className)};FastClick.prototype.needsFocus=function(target){switch(target.nodeName.toLowerCase()){case'textarea':return true;case'select':return!deviceIsAndroid;case'input':switch(target.type){case'button':case'checkbox':case'file':case'image':case'radio':case'submit':return false}return!target.disabled&&!target.readOnly;default:return(/\bneedsfocus\b/).test(target.className)}};FastClick.prototype.sendClick=function(targetElement,event){var clickEvent,touch;if(document.activeElement&&document.activeElement!==targetElement){document.activeElement.blur()}touch=event.changedTouches[0];clickEvent=document.createEvent('MouseEvents');clickEvent.initMouseEvent(this.determineEventType(targetElement),true,true,window,1,touch.screenX,touch.screenY,touch.clientX,touch.clientY,false,false,false,false,0,null);clickEvent.forwardedTouchEvent=true;targetElement.dispatchEvent(clickEvent)};FastClick.prototype.determineEventType=function(targetElement){if(deviceIsAndroid&&targetElement.tagName.toLowerCase()==='select'){return'mousedown'}return'click'};FastClick.prototype.focus=function(targetElement){var length;if(deviceIsIOS&&targetElement.setSelectionRange&&targetElement.type.indexOf('date')!==0&&targetElement.type!=='time'&&targetElement.type!=='month'&&targetElement.type!=='email'){length=targetElement.value.length;targetElement.setSelectionRange(length,length)}else{targetElement.focus()}};FastClick.prototype.updateScrollParent=function(targetElement){var scrollParent,parentElement;scrollParent=targetElement.fastClickScrollParent;if(!scrollParent||!scrollParent.contains(targetElement)){parentElement=targetElement;do{if(parentElement.scrollHeight>parentElement.offsetHeight){scrollParent=parentElement;targetElement.fastClickScrollParent=parentElement;break}parentElement=parentElement.parentElement}while(parentElement)}if(scrollParent){scrollParent.fastClickLastScrollTop=scrollParent.scrollTop}};FastClick.prototype.getTargetElementFromEventTarget=function(eventTarget){if(eventTarget.nodeType===Node.TEXT_NODE){return eventTarget.parentNode}return eventTarget};FastClick.prototype.onTouchStart=function(event){var targetElement,touch,selection;if(event.targetTouches.length>1){return true}targetElement=this.getTargetElementFromEventTarget(event.target);touch=event.targetTouches[0];if(deviceIsIOS){selection=window.getSelection();if(selection.rangeCount&&!selection.isCollapsed){return true}if(!deviceIsIOS4){if(touch.identifier&&touch.identifier===this.lastTouchIdentifier){event.preventDefault();return false}this.lastTouchIdentifier=touch.identifier;this.updateScrollParent(targetElement)}}this.trackingClick=true;this.trackingClickStart=event.timeStamp;this.targetElement=targetElement;this.touchStartX=touch.pageX;this.touchStartY=touch.pageY;if((event.timeStamp-this.lastClickTime)<this.tapDelay){event.preventDefault()}return true};FastClick.prototype.touchHasMoved=function(event){var touch=event.changedTouches[0],boundary=this.touchBoundary;if(Math.abs(touch.pageX-this.touchStartX)>boundary||Math.abs(touch.pageY-this.touchStartY)>boundary){return true}return false};FastClick.prototype.onTouchMove=function(event){if(!this.trackingClick){return true}if(this.targetElement!==this.getTargetElementFromEventTarget(event.target)||this.touchHasMoved(event)){this.trackingClick=false;this.targetElement=null}return true};FastClick.prototype.findControl=function(labelElement){if(labelElement.control!==undefined){return labelElement.control}if(labelElement.htmlFor){return document.getElementById(labelElement.htmlFor)}return labelElement.querySelector('button, input:not([type=hidden]), keygen, meter, output, progress, select, textarea')};FastClick.prototype.onTouchEnd=function(event){var forElement,trackingClickStart,targetTagName,scrollParent,touch,targetElement=this.targetElement;if(!this.trackingClick){return true}if((event.timeStamp-this.lastClickTime)<this.tapDelay){this.cancelNextClick=true;return true}if((event.timeStamp-this.trackingClickStart)>this.tapTimeout){return true}this.cancelNextClick=false;this.lastClickTime=event.timeStamp;trackingClickStart=this.trackingClickStart;this.trackingClick=false;this.trackingClickStart=0;if(deviceIsIOSWithBadTarget){touch=event.changedTouches[0];targetElement=document.elementFromPoint(touch.pageX-window.pageXOffset,touch.pageY-window.pageYOffset)||targetElement;targetElement.fastClickScrollParent=this.targetElement.fastClickScrollParent}targetTagName=targetElement.tagName.toLowerCase();if(targetTagName==='label'){forElement=this.findControl(targetElement);if(forElement){this.focus(targetElement);if(deviceIsAndroid){return false}targetElement=forElement}}else if(this.needsFocus(targetElement)){if((event.timeStamp-trackingClickStart)>100||(deviceIsIOS&&window.top!==window&&targetTagName==='input')){this.targetElement=null;return false}this.focus(targetElement);this.sendClick(targetElement,event);if(!deviceIsIOS||targetTagName!=='select'){this.targetElement=null;event.preventDefault()}return false}if(deviceIsIOS&&!deviceIsIOS4){scrollParent=targetElement.fastClickScrollParent;if(scrollParent&&scrollParent.fastClickLastScrollTop!==scrollParent.scrollTop){return true}}if(!this.needsClick(targetElement)){event.preventDefault();this.sendClick(targetElement,event)}return false};FastClick.prototype.onTouchCancel=function(){this.trackingClick=false;this.targetElement=null};FastClick.prototype.onMouse=function(event){if(!this.targetElement){return true}if(event.forwardedTouchEvent){return true}if(!event.cancelable){return true}if(!this.needsClick(this.targetElement)||this.cancelNextClick){if(event.stopImmediatePropagation){event.stopImmediatePropagation()}else{event.propagationStopped=true}event.stopPropagation();event.preventDefault();return false}return true};FastClick.prototype.onClick=function(event){var permitted;if(this.trackingClick){this.targetElement=null;this.trackingClick=false;return true}if(event.target.type==='submit'&&event.detail===0){return true}permitted=this.onMouse(event);if(!permitted){this.targetElement=null}return permitted};FastClick.prototype.destroy=function(){var layer=this.layer;if(deviceIsAndroid){layer.removeEventListener('mouseover',this.onMouse,true);layer.removeEventListener('mousedown',this.onMouse,true);layer.removeEventListener('mouseup',this.onMouse,true)}layer.removeEventListener('click',this.onClick,true);layer.removeEventListener('touchstart',this.onTouchStart,false);layer.removeEventListener('touchmove',this.onTouchMove,false);layer.removeEventListener('touchend',this.onTouchEnd,false);layer.removeEventListener('touchcancel',this.onTouchCancel,false)};FastClick.notNeeded=function(layer){var metaViewport;var chromeVersion;var blackberryVersion;var firefoxVersion;if(typeof window.ontouchstart==='undefined'){return true}chromeVersion=+(/Chrome\/([0-9]+)/.exec(navigator.userAgent)||[,0])[1];if(chromeVersion){if(deviceIsAndroid){metaViewport=document.querySelector('meta[name=viewport]');if(metaViewport){if(metaViewport.content.indexOf('user-scalable=no')!==-1){return true}if(chromeVersion>31&&document.documentElement.scrollWidth<=window.outerWidth){return true}}}else{return true}}if(deviceIsBlackBerry10){blackberryVersion=navigator.userAgent.match(/Version\/([0-9]*)\.([0-9]*)/);if(blackberryVersion[1]>=10&&blackberryVersion[2]>=3){metaViewport=document.querySelector('meta[name=viewport]');if(metaViewport){if(metaViewport.content.indexOf('user-scalable=no')!==-1){return true}if(document.documentElement.scrollWidth<=window.outerWidth){return true}}}}if(layer.style.msTouchAction==='none'||layer.style.touchAction==='manipulation'){return true}firefoxVersion=+(/Firefox\/([0-9]+)/.exec(navigator.userAgent)||[,0])[1];if(firefoxVersion>=27){metaViewport=document.querySelector('meta[name=viewport]');if(metaViewport&&(metaViewport.content.indexOf('user-scalable=no')!==-1||document.documentElement.scrollWidth<=window.outerWidth)){return true}}if(layer.style.touchAction==='none'||layer.style.touchAction==='manipulation'){return true}return false};FastClick.attach=function(layer,options){return new FastClick(layer,options)};if(typeof define==='function'&&typeof define.amd==='object'&&define.amd){define(function(){return FastClick})}else if(typeof module!=='undefined'&&module.exports){module.exports=FastClick.attach;module.exports.FastClick=FastClick}else{window.FastClick=FastClick}}());
        $(function() {
            FastClick.attach(document.body);
        });
    </script>
    <style>
        *{box-sizing:border-box;touch-action:manipulation}.pcshow{display:block}.pchide{display:none}html,body{height:100%;width:100%}body,a{margin:0;padding:0;text-decoration:none;font-family:"Microsoft YaHei",'微软雅黑',Arial;-webkit-tap-highlight-color:rgba(0,0,0,0)}#box{position:relative;height:400px;width:900px;border:2px solid #000;margin:0 auto;-webkit-user-select:none;-moz-user-select:none;-ms-user-select:none;user-select:none;overflow:hidden}#box-text{position:absolute;left:50%;top:50%;transform:translate(-50%,-120%);font-size:18px;white-space:nowrap}#retest{display:none;height:45px;width:130px;line-height:45px;color:#fff;text-align:center;background:#00aeff;margin-bottom:130px;transition:background .7s ease}#retest:hover{background:rgb(0,88,189)}.test{text-align:center;margin-top:80px}#menu-toggle{display:none;margin:0;-webkit-user-select:none;-ms-user-select:none;-moz-user-select:none;user-select:none}.head{height:90px}.head::after{content:'';display:block;height:2px;width:100%;background-image:linear-gradient(to right,#fff -30%,#559af8,#2369c7,#559af8,#fff 130%)}.head .container .logo{height:90px;width:90px;background:url('https://i.loli.net/2019/08/27/1H48VWXfsTmoaZ7.png') top left /cover no-repeat;position:absolute}.container{position:relative;height:90px;width:80%;margin:0 auto}.head .container .menu{position:absolute;left:50%;top:50%;transform:translate(-51%,-50%);font-size:0}.head .container .menu a{display:inline-block;color:#000;font-size:18px;margin:0 23px;position:relative;text-align:center}.head .menu a:after{content:'';display:block;height:2px;width:0;position:absolute;left:50%;bottom:-5px;background:#000;-moz-transition:all .7s cubic-bezier(0.57,0.01,0.29,1.3);-webkit-transition:all .7s cubic-bezier(0.57,0.01,0.29,1.3);transition:all .7s cubic-bezier(0.57,0.01,0.29,1.3)}.head .menu a:hover:after{content:"";position:absolute;width:60px;margin-left:-30px}#click-times,#time{font-size:17px}#cps-result{font-size:18px}#recording-table{margin:50px auto}table{table-layout:fixed;border-collapse:collapse;margin:20px auto;text-align:center}th{width:180px;padding:10px 30px;font-weight:normal;background-color:#444;color:#fff;border:0}td{padding:15px 0;border:solid 1px #000}tr:nth-child(1){border:solid 1px #000}tr:nth-child(odd){background:#999;color:#fff}#about-page{position:relative}#desc-infomation{display:inline-block;margin-top:150px;height:100%;width:100%;color:#222;font-size:18px;text-align:center}#footer{position:fixed;left:0;bottom:0;background:#d0d3dd;height:120px;width:100%}#footer #footer-center{position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);width:100%}#footer #copyright,#email{margin:10px;color:#5474cd;text-align:center}html .hide{display:none}html .show{display:block}.reward{display:table;color:red;font-size:45px;margin:60px auto}.wrap{height:100%;width:100%;background:rgba(119,119,119,0.5);position:fixed;left:0;top:0;z-index:1}.wrap::after{content:'';position:absolute;top:0;left:0;right:0;bottom:0;filter:blur(10px)}.wrap .alert{width:70%;background:#fff;position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);z-index:999;padding:10px}.wrap .alert .alert-head{height:30px}.wrap .close{display:inline-block;height:30px;width:30px;position:absolute;right:0;top:0;font-size:20px;color:#222;text-align:center;line-height:30px;-moz-transition:all .55s;-webkit-transition:all .55s;transition:all .55s}.wrap .close:hover{background:red;color:#fff}.wrap .alert .qrcodes{text-align:center;margin:18px 0}.wrap .alert .qrcodes img{display:inline-block}#lowbrowser{height:50px;width:100%;background:pink;color:red;text-align:center;line-height:50px}
    </style>
    <style>
        @media screen and (max-width:900px){.test{width:100%;box-sizing:border-box;padding-left:5px;padding-right:5px;margin-top:40px}#box{height:300px;width:100%;border:2px solid #000}.pcshow{display:none}.pchide{display:block}#menu-toggle{display:inline-block;position:absolute;right:0;top:50%;transform:translateY(-50%);font-size:28px}.head{border:0}.head .container .logo{height:60px;width:60px;position:relative;top:50%;transform:translateY(-50%)}html .mb-menu{position:relative;z-index:10;height:150px;width:100%;float:left;margin-bottom:18px}html .mb-menu a{display:block;height:50px;color:#fff;line-height:50px;text-align:center;background:#555}#desc-infomation{margin-top:10%;text-align:left}}
    </style>
    <style>
        @media screen and (max-width:410px){table{margin:0;width:100%}th{margin:0;width:25%;padding:5px}td{padding:5px}}@media screen and (max-height:530px){html #box{height:200px}html #desc-infomation{position:static;transform:inherit;height:auto;width:100%;padding:0px 15px 0px 15px}#footer{position:static;background:#d0d3dd;height:auto;width:100%}#footer #footer-center{position:static;transform:inherit;width:100%;padding:12px}#footer #copyright,#email{margin:10px;color:#5474cd;text-align:center}}
    </style>
    <style>
        @media screen and (max-width:779px){html .wrap .alert{width:100%}html .wrap .alert .qrcodes{display:none}html .wrap .alert p{margin:10px}html .wrap .alert .qrcodes-min{display:block;text-align:center}html .wrap .alert .qrcodes-min .qr-box{display:inline-block;margin:5px 15px 0}}
    </style>
    <title>在线CPS测试_鼠标点击速度测试</title>
</head>
<body>
    <!--[if lt IE 10]><div id="lowbrowser">你的浏览器实在是<strong>太太太</strong>旧了, 请升级你的浏览器！否则无法正常使用！<a href="https://browsehappy.com/" style="text-decoration: underline; color: red;"><strong>立即升级</strong></a></div><![endif]-->
    <div class="head">
        <div class="container">
            <div class="logo"></div>
            <p id="menu-toggle" class="iconfont">&#xe621;</p>
            <div class="menu pcshow">
                <a href="javascript:;" class="hp">首页</a>
                <a href="javascript:;" class="record">记录</a>
                <a href="javascript:;" class="desc">说明</a>
            </div>
        </div>
        <div class="mb-menu pchide hide">
            <a href="javascript:;" class="hp">首页</a>
            <a href="javascript:;" class="record">记录</a>
            <a href="javascript:;" class="desc">说明</a>
        </div>
    </div>
    <div id="home-page">
        <div class="test">
            <div id="box">
                <p id="box-text">paly</p>
            </div>
            <p id="time">0.00s</p>
            <p id='click-times'>你一共点击了: 0次</p>
            <p id="cps-result" style="display: none;"></p>
            <a href="javascript:;" id="retest">0</a>
        </div>
        <div id="footer">
            <div id="footer-center">
                <a href="http://www.5vmc.com/cps?from=gitee" title="cps测试" target="_blank"><p id="copyright">CPS测试</p></a>
                <p id="copyright">Minecraft</p>
            </div>
        </div>
    </div>
    <div id="recording-page" style="display: none">
        <p id="never-test" style="margin-top: 15%; text-align: center; font-size: 22px; color: #444;">你还没有进行过测试!</p>
        <table border="1" id="recording-table" style="display: none;">
            <tr>
                <th>点击次数</th>
                <th>最高CPS</th>
                <th>最低CPS</th>
                <th>平均CPS</th>
            </tr>
        </table>
        <div id="footer">
            <div id="footer-center">
                <a href="http://www.5vmc.com/cps?from=gitee" title="cps测试" target="_blank"><p id="copyright">CPS测试</p></a>
                <p id="copyright">Minecraft</p>
            </div>
        </div>
    </div>
    <div id="about-page" style="display: none">
        <p id="desc-infomation">在你第一次点击测试区域时，开始计时。为了精准最后的结果，我们会记录你10秒内所有的点击，并计算平均值。最后展示你的CPS.</p>
        <a href="javascript:;" class="reward iconfont">&#xe610;</a>
        <div class="wrap hide">
            <div class="alert">
                <div class="alert-head">
                    <a href="javascript:;" class="btn close iconfont">&#xe608;</a>
                </div>
                <div class="alert-body">
                    <p class="msg">&nbsp&nbsp&nbsp&nbsp你是傻种吗？瞎胡点 </p>
                    <div class="qrcodes">
                        <img src="u=3240108947,375155911&fm=26&gp=0.jpg">
                    </div>
                    <div class="qrcodes-min hide">
                        <div class="qr-box">
                            <img src="https://i.loli.net/2019/12/02/jQkAfaeRvyqmXu2.png" alt="" height="100px" width="100px">
                            <p>花呗红包</p>
                        </div>
                        <div class="qr-box">
                            <img src="https://i.loli.net/2019/12/02/b9ciS2DgBZP1QYU.png" alt="" height="100px" width="100px">
                            <p>支付宝</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div id="footer">
            <div id="footer-center">
                <a href="http://www.5vmc.com/cps?from=gitee" title="cps测" target="_blank"><p id="copyright">CPS测试</p></a>
                <p id="copyright">Minecraft</p>
            </div>
        </div>
    </div>
    <script>
        $(function(){   // width > 900 ? 菜单隐藏 : null
            $(window).resize(function(){
                var height = $(window).height();
                var width = $(window).width();
                if( width > 900 ) {
                    $('.mb-menu').removeAttr('style');
                }
            });
        });
    </script>
    <script>
        // 功能
        function CpsTest() {
            this.testing = false;
            this.running = false;
            this.cpsArr = [];
            this.counter = 0;
            this.temp = 0;
            this.temp2 = 0;
        }
        var cpsTest = new CpsTest();
        CpsTest.prototype.count = function () {
            if(cpsTest.timer2 == null) {
                function eachClick() {
                    cpsTest.temp = cpsTest.counter;
                    cpsTest.counter = 0;
                    cpsTest.temp2 += cpsTest.temp;
                    cpsTest.cpsArr.push(cpsTest.temp);
                    if(cpsTest.sec == 10){
                        clearInterval(cpsTest.timer2);
                        var clickTimes = 0;
                        cpsTest.cpsArr.map(function (item){
                            return clickTimes += item;
                        });
                        $('#retest').css('display', 'inline-block');
                        $('#cps-result').css('display', 'block');
                        $('#cps-result').text( '你的CPS是: ' + (clickTimes/10));
                        var max = cpsTest.cpsArr[0], min = cpsTest.cpsArr[0];
                        for( var i = 0; i < cpsTest.cpsArr.length; i++) {
                            var cur = cpsTest.cpsArr[i];
                            max < cur? max = cur: null;
                        }
                        for(var i = 0; i < cpsTest.cpsArr.length; i++ ){
                            var cur2 = cpsTest.cpsArr[i];
                            min > cur ? min = cur: null;
                        }
                        $('#never-test').css('display', 'none');
                        $('#recording-table').css('display', 'table');
                        $('#recording-table').append('<tr><td>' + clickTimes + '</td><td>' + max + '</td><td>' + min + '</td><td>' + (clickTimes/10) + '</td></tr>');
                    }
                }
                cpsTest.timer2 = setInterval(eachClick, 1000);
            }
            if(cpsTest.testing){
                cpsTest.counter++;
                var totalClick = cpsTest.temp2 + cpsTest.counter;
                $('#click-times').text('你一共点击了: ' + totalClick + '次');
            }
        };
        CpsTest.prototype.time = function () {
            var date = new Date();
            cpsTest.testing = true;
            cpsTest.running = true;
            cpsTest.ms = Math.floor((date.getTime() - st)%1000/10);
            cpsTest.sec = Math.floor((date.getTime() - st)%60000/1000);
            cpsTest.ms = cpsTest.ms < 10 ? '0' + cpsTest.ms : cpsTest.ms;
            $('#time').text(cpsTest.sec + '.' + cpsTest.ms + 's');
            if(cpsTest.sec == 10){
                cpsTest.ms = 0;
                clearInterval(cpsTest.timer);
                $('#time').text('10.00s');
                cpsTest.testing = false;
            }
        };
    </script>
    <script>
        //交互
        var oBox = document.getElementById('box');
        var st = 0;

        var oHp = document.getElementsByClassName('hp');
        var oRecording = document.getElementsByClassName('record');
        var oDesc = document.getElementsByClassName('desc');
        var mbMenuBtn = $('#menu-toggle')[0];
        var open = false;

        for(var i = 0; i < oHp.length; i++) {
            oHp[i].onclick = function () {
                $('#home-page').css('display', 'block');
                $('#recording-page').css('display', 'none');
                $('#about-page').css('display', 'none');
                $('.mb-menu:eq(0)').slideUp();
            }
        }

        for(var i = 0; i < oRecording.length; i++) {
            oRecording[i].onclick = function () {
                $('#home-page').css('display', 'none');
                $('#recording-page').css('display', 'block');
                $('#about-page').css('display', 'none');
                $('.mb-menu:eq(0)').slideUp(300);
            }
        }

        for(var i = 0; i < oDesc.length; i++) {
            oDesc[i].onclick = function () {
                $('#home-page').css('display', 'none');
                $('#recording-page').css('display', 'none');
                $('#about-page').css('display', 'block');
                $('.mb-menu:eq(0)').slideUp(300);
            }
        }
        mbMenuBtn.addEventListener('click', function () {
            if( open == false ) {
                open = true;
                $('.mb-menu').stop(true,true).slideDown();
            } else if( open ) {
                open = false;
                $('.mb-menu').stop(true,true).slideUp();
            }
        });


        if(/Android|webOS|iPhone|iPod|BlackBerry/i.test(navigator.userAgent)) {
			$('#box').click(function () {
                if(!cpsTest.testing && !cpsTest.running){
                    cpsTest.testing = true;
                    st = new Date().getTime();
                    cpsTest.timer = setInterval(cpsTest.time, 10);
                }
                cpsTest.count();
            })
		} else {
            oBox.addEventListener('mousedown', function (event) {
            var e = event || window.event;
            if( e.button != 0 ) return;
            if(!cpsTest.testing && !cpsTest.running){
                cpsTest.testing = true;
                st = new Date().getTime();
                cpsTest.timer = setInterval(cpsTest.time, 10);
            }
            cpsTest.count();
            oBox.style.borderColor = '#8d8d8d';
            $('#box-text').css('color', '#8d8d8d');
        });
        }
        oBox.onmouseup = function () {
            oBox.style.borderColor = '#000';
            $('#box-text').css('color', '#000');
        };

        $('body').mouseover(function (e) {
            if ( $(e.target).closest('#box').length == 0 ) {
                oBox.onmouseup();
            }
        });
        $('#retest').click(function () {
            cpsTest = new CpsTest;
            $('#cps-result').css('display', 'none');
            $('#click-times').text('你一共点击了: 0次');
            $('#retest').css('display', 'none');
            $('#time').text('0.00s');
        });
        
        var closeBtn = document.getElementsByClassName('close')[0];
        var rewardBtn = document.getElementsByClassName('reward')[0];

        rewardBtn.onclick = function () {
            $('.wrap').eq(0).fadeIn(520, function () {
                $('.wrap').eq(0).removeAttr('style');
                $('.wrap').eq(0).removeClass('hide');
            });
        }
        closeBtn.onclick = function () {
            $('.wrap').eq(0).addClass('hide');
        }
        document.onclick = function (e) {
            var menuOpened = document.getElementsByClassName('mb-menu')[0].style.display; 
            var menuToggleBtn = document.getElementById('menu-toggle');
            if ( e.target != menuToggleBtn && menuOpened == 'block'){
                $('.mb-menu').stop(true,false).slideUp(350);
            }
        }
    </script>
</body>
</html>
