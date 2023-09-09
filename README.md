(function (){
    function getBasePath() {
        var basePath, scripts = document.getElementsByTagName('script');
        for (var i = 0; i < scripts.length; i++) {
            var script = scripts[i];
            if (script.src === undefined) { continue; }
            var srcParts = script.src.split('/');
            var lastPart = srcParts.pop().toLowerCase();
            if (lastPart === 'justwidget.js' || lastPart === 'justwidget.js?force=true') {
                basePath = srcParts.splice(0, srcParts.length - 2).join('/');
                break;
            }
        }
        return basePath;
    }
    function initJs() {
        window.JustWidgetBasePath = getBasePath();
        var script = document.createElement('script');
        script.type = 'text/javascript';
        script.charset="utf-8";
        window.JustWidgetAttributes = {"senderName":"MathQuizBot","options":{"headline":{"text":"","hide":"Свернуть","show":false},"names":{"assistantName":"","userName":"","show":false},"captions":{"inputPlaceholder":"","loadHistory":"Загрузить историю сообщений","errorOccurred":"Возникла ошибка","viewLog":"посмотреть лог ошибки","errorLog":"Лог ошибки","copyLog":"Скопировать лог","closeLog":"Закрыть","imageDownload":"Закрыть","dndLabel":"Перетащите файл сюда"},"sessionByUserMessage":{"show":false,"welcomemessage":"","delay":0,"buttonsShow":false,"buttons":[]},"bubble":{"show":false,"delay":10,"bubbletext":"","mobileBubbletext":""},"involvement":{"enabled":false,"events":[]},"position":"right","fileUpload":{"show":false,"uploadErrorMessage":"","tooBigFileMessage":""},"showLogo":false,"logo":"","channel":null,"percentage":100,"blockForm":{"show":false},"sendBtn":{"show":false},"avatar":{"show":false,"assistantAvatarUrl":"","userAvatarUrl":"","operatorAvatarUrl":"","size":24},"linkPreview":{"show":true},"positionOffset":{"bottom":24,"right":24},"palette":{"headlineBackgroundColor":"#5A9CED","headlineTextColor":"dark","chatBackgroundColor":"#FFFFFF","chatBackgroundOpacity":100,"userMessageBackgroundColor":"#CBDFF8","userMessageTextColor":"dark","botMessageBackgroundColor":"#F4F5F5","botMessageTextColor":"dark","formButtonsColor":"#5A9CED","formTextColor":"#000"},"font":"Roboto","sizes":{"font":"small","avatar":"big"},"blinkOnNewMessage":true,"buttonsSamePlace":false,"soundNotification":{"option":"none","sound":""},"embedmentContainer":{"id":"","enabled":false},"showCloseButton":false,"showSpinner":true,"hidePoweredByJustAI":false},"theme":"defaultv3","position":"right","percentage":100};
        window.JustWidgetName = "1000079834-mathquizbot-1000079834-ujV-20943253011";
        script.src = window.JustWidgetBasePath + "/s/" + window.JustWidgetAttributes.theme + "/js/index.js";
        script.dataset.origin='justwidget';

        document.body.appendChild(script);

        if (!window.JustWidgetAttributes.options.notUseStyles) {
            var style = document.createElement('link');
            style.rel = 'stylesheet';
            style.href = window.JustWidgetBasePath + "/s/" + window.JustWidgetAttributes.theme + "/css/index.css";
            style.dataset.origin='justwidget';

            document.head.appendChild(style);
        }
    }

    function addPolyfill() {
        window.JustWidgetBasePath = getBasePath();
        var script = document.createElement('script');
        script.type = 'text/javascript';
        script.charset="utf-8";
        script.src = window.JustWidgetBasePath + "/s/ie.js";
        script.dataset.origin='justwidget';
        var done = false;

        script.onload = script.onreadystatechange = function() {
            if (!done && (!this.readyState || this.readyState === 'loaded' || this.readyState === 'complete')) {

                done = true;

                initJs();

                script.onload = script.onreadystatechange = null;

            }

        };
        document.body.appendChild(script);

    };

    var isIE11 = !!window.MSInputMethodContext && !!document.documentMode;

    if(isIE11 || /Edge/.test(navigator.userAgent)){
        addPolyfill()
    }
    else{
        initJs();
    }


})();
 
