<template>
    <header id="headerType" :class="fonts">
      <div className="header__inner">
        <div className="header__logo">
          <a href="/">
            web <em>site</em>
          </a>
        </div>
        <nav class="header__menu">
          <ul>
            <li>
              <a href="#imageType">이미지 영역</a>
            </li>
            <li>
              <a href="#imgTextType">텍스트 영역</a>
            </li>
            <li>
              <a href="#cardType">배너 영역</a>
            </li>
            <li>
              <a href="#bannerType">컨텐츠 영역</a>
            </li>
            <li>
              <a href="#textType">푸터 영역</a>
            </li>
          </ul>
        </nav>
        <div class="header__member">
          <a href="/">로그인</a>
        </div>
        <div class="header__ham">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
    </header>
</template>

<script>
export default{
    props: {
        fonts: String ,
    },
} 
</script>

<style>
/* headerType */
.header__inner {
    width: 100%;
    height: 70px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 20px;
    box-sizing: border-box;
    border-bottom: 1px solid #ccc;
    position: fixed;
    left: 0;
    top: 0;
    z-index: 10000;
    background: #fff;
}
.header__logo {
    width: 20%;
    font-size: 30px;
    font-weight: 700;
    text-transform: uppercase;
}
.header__logo em {
    font-size: 18px;
    font-weight: 400;
}
.header__menu {
    width: 60%;
    text-align: center;
}
.header__menu li {
    display: inline;
}
.header__menu li a {
    padding: 13px 30px;
    margin: 0 5px;
    transition: background-color 0.3s;
}
.header__menu li a:hover {
    background-color: #f1f1f1;
    border-radius: 5px;
}
.header__member {
    width: 20%;
    text-align: right;
}
.header__member a {
    font-size: 16px;
    border: 1px solid #000;
    padding: 10px 30px;
    border-radius: 50px;
    transition: background-color 0.3s;
}
.header__member a:hover {
    background-color: #000;
    color: #fff;
}
.header__ham {
    position: absolute;
    right: 10px;
    top: 10px;
    z-index: 1000;
    width: 50px;
    height: 50px;
    display: none;
    cursor: pointer;
}
.header__ham span {
    display: block;
    background: #000;
    width: 30px;
    height: 2px;
    border-radius: 3px;
    margin-left: 10px;
    margin-top: 5px;
    transition: 0.25s margin 0.25s, 0.25s transform;
}
.header__ham span:nth-child(1){
    margin-top: 18px;
}
.header__ham.active span {
    transition: 0.25s margin, 0.25s transform 0.25s;
}
.header__ham.active span:nth-child(1){
    margin-top: 25px;
    margin-bottom: -7px;
    transform: rotate(45deg);
}
.header__ham.active span:nth-child(2){
    transform: rotate(45deg);
}
.header__ham.active span:nth-child(3){
    margin-top: -2px;
    transform: rotate(135deg);
}

/* media */
@media (max-width: 1300px){
    .header__menu {
        position: fixed;
        right: -100%;
        top: 69px;
        background: #fff;
        width: 60%;
        height: 100vh;
        padding: 20px;
        text-align: right;
        transition: right 0.4s ease-in;
    }
    .header__menu ul li {
        display: block;
        margin: 20px;
    }
    .header__menu ul li a {
        padding: 10px;
        white-space: nowrap;
    }
    .header__menu.active {
        right: 0;
    }
    .header__member {
        margin-right: 50px;
    }
    .header__ham {
        display: block;
    }
    .header__logo {
        width: 50%;
    }
    .header__member {
        width: 50%;
    }
}
@media (max-width: 600px){
    .header__inner {
        border-bottom: 0;
    }
    .header__logo {
        font-size: 24px;
    }
    .header__member a {
        padding: 7px 17px;
    }
}
</style>