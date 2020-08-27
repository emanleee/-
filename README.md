-
<!DOCTYPE html>
<html lang="zh-tw">

<head>
    <title>登入 ｜卡提諾論壇</title>
    <meta charset="UTF-8" />
    <meta name="viewport"
        content="width=device-width, initial-scale=1.0, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0">
    <meta name="keywords" itemprop="keywords" content="論壇,ck101,卡提諾,卡提諾論壇,卡提諾正妹,時事,宅宅,新奇,貼圖,小說,搞笑,娛樂,運動,生活,話題" />
    <meta name="description"
        content="卡提諾論壇是一個綜合性大型討論區，卡提諾論壇有多元豐富的討論看版與主題：正妹,新聞,新奇,貼圖,小說,搞笑,娛樂,科技,生活,話題等，是最用心經營的網路社群！" />
    <meta name="generator" content="ck101.com" />
    <meta name="author" content="ck101.com" />

    <meta property="og:site_name" name="application-name" content="卡提諾論壇" />
    <meta property="og:type" content="website" />
    <meta property="og:title" content="登入 ｜卡提諾論壇" />
    <meta property="og:description" content=",卡提諾論壇" />
    <meta property="og:url" content="https://auth.ck101.com/index.php" />
    <meta property="og:image" content="http://sla.ckcdn.com/static/image/common/cklogo_290.png" />

    <link rel="dns-prefetch" href="//s1.imgs.cc">
    <link rel="dns-prefetch" href="//s2.imgs.cc">
    <link rel="dns-prefetch" href="//s3.imgs.cc">

    <link rel="stylesheet" type="text/css" href="assets/css/common.css" />
</head>

<body>
    <header>
        <div class="mobileLogo">
            <img src="//s1.imgs.cc/img/UtE3Ls7.png" alt="" />
        </div>
    </header>
    <section class="input_form">
        <form name="loginFrm" method="post"
            action="?act=dologin&app_id=ck101-lottery&scope=profile%2Ccredit%2Cforum&redirect_uri=https%3A%2F%2Flottery.ck101.com%2Fauth"
            onsubmit="return onLoginSubmit();">
            <div class="fbLoginSection">
                <div class="btnWrap facebookWrap" onclick="fbLoginHandler.onclick();">
                    <div class="fbLoginBtn">
                        <div class="icon"></div>
                        <div class="text">使用 Facebook 登入</div>
                    </div>
                </div>
                <div class="btnWrap googleWrap" onclick="googleLoginHandler.onclick();">
                    <div class="googleLoginBtn">
                        <div class="icon"></div>
                        <div class="text">使用 Google 登入</div>
                    </div>
                </div>
                <div class="btnWrap appleWrap" onclick="appleLoginHandler.onclick();">
                    <div class="appleLoginBtn">
                        <div class="icon"></div>
                        <div class="text">使用 Apple 登入</div>
                    </div>
                </div>
            </div>
            <div class="input_field">
                <span class="input_fieldTitle">帳號</span>
                <span class="input_errorMsg" id="errorAccount"></span>
                <input type="text" name="username" placeholder="UID/用戶名/EMAIL" tabindex="1"
                    onkeyup="_removeClass(this, 'with_error'); removeSiblingErMsg(this, 'input_errorMsg');" />
            </div>
            <div class="input_field">
                <span class="input_fieldTitle">密碼</span>
                <span class="input_errorMsg" id="errorPasswd"></span>
                <a class="lostpw" href="//ck101.com/member.php?mod=logging&amp;action=login&amp;viewlostpw=1"
                    target="_blank">忘記密碼？</a>
                <input type="password" name="passwd" autocomplete="off" placeholder="你的密碼" tabindex="2"
                    onkeyup="_removeClass(this, 'with_error'); removeSiblingErMsg(this, 'input_errorMsg');" />
            </div>
            <div class="input_field">
                <select name="question_id" tabindex="3">
                    <option value="0">安全提問（未設置請忽略）</option>
                    <option value="1">母親的名字</option>
                    <option value="2">爺爺的名字</option>
                    <option value="3">父親出生的城市</option>
                    <option value="4">您其中一位老師的名字</option>
                    <option value="5">您個人計算機的型號</option>
                    <option value="6">您最喜歡的餐館名稱</option>
                    <option value="7">駕駛執照最後四位數字</option>
                </select>
                <img class="login_question_arrow" src="//s2.imgs.cc/img/l1fI2Aj.png" alt="" />
            </div>
            <div class="input_field">
                <span class="input_fieldTitle">你的回答</span>
                <span class="input_errorMsg" id="errorSecurity"></span>
                <input type="text" name="answer" autocomplete="off" placeholder="輸入答案" tabindex="4"
                    onkeyup="_removeClass(this, 'with_error'); removeSiblingErMsg(this, 'input_errorMsg');" />
            </div>
            <div class="input_field">
                <input class="filledTypeBtn" type="submit" value="帳號登入" tabindex="5" />
            </div>
            <div class="input_field">
                <input class="lineTypeBtn" type="button" value="註冊" tabindex="6"
                    onclick="window.location.href = '?act=register&app_id=ck101-lottery&scope=profile%2Ccredit%2Cforum&redirect_uri=https%3A%2F%2Flottery.ck101.com%2Fauth';" />
            </div>
        </form>
    </section>

    <script type="text/javascript">
        function _removeClass(element, className) {
            /* HTML 5 compliant browsers. */
            if (!!document.body.classList) {
                element.classList.remove(className);
                return;
            }
            /* Legacy browsers (IE<10) support. */
            element.className = element.className.replace(new RegExp("(^|\\s+)" + className + "(\\s+|$)"), ' ').replace(/^\s+/, '').replace(/\s+$/, '');
        }
        function removeSiblingErMsg(elem, cls) {

            function hasClass(el, cls) {
                return (' ' + el.className + ' ').indexOf(' ' + cls + ' ') > -1;
            }

            while ((elem = elem.previousSibling) && !hasClass(elem, cls));
            elem.innerHTML = '';
            // return elem ? elem.parentNode.removeChild(elem) : false;
        }
        function onLoginSubmit() {
            var frm = document.loginFrm;
            if (!frm)
                return false;

            if (!frm.username || frm.username.value.length == 0) {
                document.getElementById('errorAccount').innerHTML = '請輸入 UID/用戶名/EMAIL';
                return false;
            }

            if (!frm.passwd || frm.passwd.value.length == 0) {
                document.getElementById('errorPasswd').innerHTML = '請輸入密碼';
                return false;
            }

            if ((!frm.question_id || parseInt(frm.question_id.value) > 0) &&
                (!frm.answer || frm.answer.value.length == 0)) {
                document.getElementById('errorSecurity').innerHTML = '';
                alert('請輸入安全提問答案');
                return false;
            }

            return true;
        }

        var fbLoginHandler = {
            _lock: false,
            onclick: function () {
                if (!this._lock) {
                    this._lock = true;
                    setTimeout(function () {
                        this._lock = false;
                    }.bind(this), 2000);
                }
                else {
                    return;
                }

                setTimeout(function () { window.location.href = '?act=fblogin&app_id=ck101-lottery&scope=profile%2Ccredit%2Cforum&redirect_uri=https%3A%2F%2Flottery.ck101.com%2Fauth'; }, 200);
            }
        };

        var googleLoginHandler = {
            _lock: false,
            onclick: function () {
                if (!this._lock) {
                    this._lock = true;
                    setTimeout(function () {
                        this._lock = false;
                    }.bind(this), 2000);
                }
                else {
                    return;
                }

                setTimeout(function () { window.location.href = '?act=googlelogin&app_id=ck101-lottery&scope=profile%2Ccredit%2Cforum&redirect_uri=https%3A%2F%2Flottery.ck101.com%2Fauth'; }, 200);
            }
        };

        var appleLoginHandler = {
            _lock: false,
            onclick: function () {
                if (!this._lock) {
                    this._lock = true;
                    setTimeout(function () {
                        this._lock = false;
                    }.bind(this), 2000);
                }
                else {
                    return;
                }

                setTimeout(function () { window.location.href = '?app_id=ck101-official&act=applelogin&app_id=ck101-lottery&scope=profile%2Ccredit%2Cforum&redirect_uri=https%3A%2F%2Flottery.ck101.com%2Fauth'; }, 200);
            }
        };
    </script>
</body>

</html>
