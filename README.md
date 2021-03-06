
:root {
  --primary-text-color: #757575;
  --title-text-color: #212121;
  --accent-color: #2196f3;
  --button-hover: #188ce8;
  --white-color: #ffffff;
  --section-color: #2f303a;
  --logo-color: #afb1b8;
  --button-bgc: #f5f4fa;
  --transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
}

body {
  background-color: var(--white-color);
  color: var(--primary-text-color);
  font-family: Roboto, sans-serif;
}

/* сброс стилей */
h1,
h2,
h3,
p {
  margin: 0;
}

/*для скрытия маркеров и боковых отступов*/
ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

/* img */
img {
  display: block; 
  max-width: 100%;
  height: auto;
}

/*для скрытия подчеркивания*/
a {
  text-decoration: none;
}

/* скрытие заголовков */
.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  border: 0;
  padding: 0;
  white-space: nowrap;
  clip-path: inset(100%);
  clip: rect(0 0 0 0);
  overflow: hidden;
}

/* для центрирования и ограничечения контента по ширине */
.container {
  width: 1200px;
  margin: 0 auto;
  padding-left: 15px;
  padding-right: 15px;
}

/* Верхний и нижний отступ */
.section {
  padding: 94px 0;
}

/*логотип*/
.logo {
  margin-right: 93px;
  color: #000000;
  font-family: Raleway;
  font-size: 26px;
  line-height: 1.19;
  letter-spacing: 0.03em;
}

.logo-icon {
  color: var(--accent-color);
}

/*навигация*/
.header-container {
  display: flex;
  align-items: center;
  padding-top: 25px;
  padding-bottom: 25px;
}
.site-nav {
  display: flex;
}

.site-nav__item:not(:last-child) {
  margin-right: 50px;
}

.site-nav__link {
  color: var(--title-text-color);
  font-weight: 500;
  font-size: 14px;
  line-height: 1.14;
  letter-spacing: 0.02em;

   transition: color 250ms var(--transition-timing-function);
}

.site-nav__link:hover,
.site-nav__link:focus {
  color: var(--accent-color);
}

.site-nav__link--active {
  color: var(--accent-color);
}

.site-nav__item {
  position: relative;
}

.site-nav__link--active::after {
  display: inline-block;
  position: absolute;
  content: '';
  bottom: -32px;
  left: 0;

  background-color: var(--accent-color);
  width: 100%;
  height: 4px;
  border-radius: 2px;

  transform: scale(1);
  transition: transform 250ms var(--transition-timing-function);
}

.site-nav__link--active:hover::after {
  transform: scaleX(0.9);
}

/* рамка под хедером */
.page-header {
  border-bottom: 1px solid #ececec;
}

/*контакты*/
.contacts {
  display: flex;
  margin-left: auto;
}

.contacts__item:not(:last-child) {
  margin-right: 50px;
}

.contacts__link {
  display: flex;
  align-items: center;
  color: var(--primary-text-color);
  fill: var(--primary-text-color);
  font-weight: 500;
  font-size: 14px;
  line-height: 1.4;
  letter-spacing: 0.02em;
  margin-bottom: 0;

  transition: color 250ms var(--transition-timing-function),
    fill 250ms var(--transition-timing-function);
}

.contacts__logo {
  margin-right: 10px;
}

.contacts__link:hover,
.contacts__link:focus {
  color: var(--accent-color);
  fill: var(--accent-color);
} 

/*----------------------index.html-----------------------*/

/* hero */
.hero {
  padding: 200px 0;
  text-align: center;
  margin: 0 auto;
  max-width: 1600px;
  height: 600px;
  background-image: linear-gradient(to right, rgba(47, 48, 58, 0.4), rgba(47, 48, 58, 0.4)),
    url('../images/hero.jpg');
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  background-color: var(--section-color);
}

.hero__title {
  margin-bottom: 30px;
  color: var(--white-color);
  font-weight: 900;
  font-size: 44px;
  line-height: 1.36;
  letter-spacing: 0.06em;
  text-transform: uppercase;
}

.hero__button {
  padding: 10px 32px;
  min-width: 200px;
  min-height: 50px;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15);
  border-radius: 4px;
  border: transparent;

  align-items: center;
  text-align: center;
  letter-spacing: 0.06em;

  background-color: var(--accent-color);
  color: var(--white-color);
  cursor: pointer;
  font-weight: 700;
  font-size: 16px;
  line-height: 1.88;

  transition: background-color 250ms var(--transition-timing-function);
}

.hero__button:hover,
.hero__button:focus {
  background-color: var(--button-hover);
}


/* ---------------------Модальное окно-------------------- */
.backdrop {
  visibility: visible;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.2);

  opacity: 1;
  transition: opacity 250ms var(--transition-timing-function),
    visibility 250ms var(--transition-timing-function);
}

.backdrop.is-hidden {
  visibility: hidden;
  opacity: 0;
  pointer-events: none;
}

.backdrop.is-hidden .modal-box {
  transform: translate(-50%, -50%) scale(0);
}

.modal-box {
  position: absolute;
  top: 50%;
  left: 50%;

  padding: 40px;
  min-width: 528px;

  background-color: var(--white-color);
  box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.12), 0px 1px 1px rgba(0, 0, 0, 0.14),
    0px 2px 1px rgba(0, 0, 0, 0.2);
  border-radius: 4px;

  transform: translate(-50%, -50%) scale(1);

  transition: transform 250ms var(--transition-timing-function);
}

.modal-box__btn {
  position: absolute;
  top: 8px;
  right: 8px;

  display: flex;
  justify-content: center;
  align-items: center;

  margin-left: auto;
  width: 30px;
  height: 30px;

  background-color: var(--white-color);
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 50%;
}

.modal-box__btn--close {
  fill: #000000;
  cursor: pointer;

  transition: fill 250ms var(--transition-timing-function);
}

.modal-box__btn--close:hover,
.modal-box__btn--close:focus {
  fill: var(--accent-color);
}

/* modal-form */
.modal-box__title {
  margin-bottom: 12px;
  font-weight: 700;
  font-size: 20px;
  line-height: 1.15;
  text-align: center;
  letter-spacing: 0.03em;

  color: #212121;
}

.modal-box__form {
  width: 448px;
  margin: 0 auto;
  text-align: center;
}

.modal-box__field {
  display: flex;
  flex-direction: column;
  position: relative;
  margin-bottom: 10px;
}

.modal-box__label {
  margin-bottom: 10px;
  text-align: start;

  font-weight: 400;
  font-size: 12px;
  line-height: 1.17;
  margin-bottom: 4px;

  letter-spacing: 0.01em;

  color: var(--primary-text-color);
}

.modal-box__input {
  height: 40px;
  padding: 11px 12px 11px 42px;

  border: 1px solid rgba(33, 33, 33, 0.2);
  box-sizing: border-box;
  border-radius: 4px;

  transition: border-color 250ms var(--transition-timing-function),
    outline 250ms var(--transition-timing-function);
}

.modal-box__input:focus,
.modal-box__input:focus + .modal-box__icon {
  fill: var(--accent-color);
  border-color: var(--accent-color);
  outline: none;
}

.modal-box__icon {
  position: absolute;
  top: 50%;
  left: 12px;

  fill: var(--title-text-color);

  transition: fill 250ms var(--transition-timing-function);
}

.textarea {
  display: flex;
  flex-direction: column;
  position: relative;
  margin-bottom: 20px;
}

.textarea__field {
  padding: 12px 16px;
  width: 448px;
  border: 1px solid rgba(33, 33, 33, 0.2);
  box-sizing: border-box;
  border-radius: 4px;

  resize: none;
  transition: border-color 250ms var(--transition-timing-function),
    outline 250ms var(--transition-timing-function);
}

.textarea__field:focus {
  border-color: var(--accent-color);
  outline: none;
}

.textarea__field::placeholder {
  font-weight: 400;
  font-size: 12px;
  line-height: 14px;
  letter-spacing: 0.01em;

  color: rgba(117, 117, 117, 0.5);
  transition: color 250ms var(--transition-timing-function);
}

.textarea__field:focus::placeholder {
  color: var(--accent-color);
}

.modal-policy {
  display: flex;
  justify-content: center;
  margin-bottom: 30px;
  padding: 0;
}

.modal-policy__label {
  display: inline-flex;
  align-items: center;
}

.modal-policy__check {
  display: inline-block;
  margin-right: 8px;
  width: 16px;
  height: 15px;
  border: 2px solid var(--title-text-color);
  border-radius: 2px;
  transform: scale(0.9);

  transition: transform 250ms var(--transition-timing-function),
    background-color 250ms var(--transition-timing-function),
    border-color 250ms var(--transition-timing-function);
}

.modal-policy__input:checked + .modal-policy__check {
  background-color: #2196f3;
  border-color: #2196f3;
  background-image: url(../images/icon-check.svg);
  background-size: contain;

  background-origin: border-box;
  transform: scale(1);
}

.modal-policy__text {
  font-size: 14px;
  line-height: 1.71;

  letter-spacing: 0.03em;
  color: #757575;
}

.modal-policy__agreement {
  position: relative;
  text-decoration: none;

  font-size: 14px;
  line-height: 1.71;

  letter-spacing: 0.03em;
  color: var(--accent-color);
}

.modal-policy__agreement::after {
  position: absolute;
  content: '';
  top: 14.5px;
  left: 0;
  width: 100%;
  height: 1px;
  background-color: var(--accent-color);
}

.modal__submit {
  width: 200px;
  height: 50px;
  padding: 10px 55px;

  background-color: var(--accent-color);
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15);
  border-radius: 4px;
  border-style: none;
  cursor: pointer;

  font-weight: 700;
  font-size: 16px;
  line-height: 1.88;

  align-items: center;
  text-align: center;
  letter-spacing: 0.06em;

  color: #ffffff;

  transition: background-color 250ms var(--transition-timing-function);
}

.modal__submit:hover,
.modal__submit:focus {
  background-color: var(--button-hover);
}
/*---------------Особенности------------*/

.feature__title--visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  border: 0;
  padding: 0;
  white-space: nowrap;
  clip-path: inset(100%);
  clip: rect(0 0 0 0);
  overflow: hidden;
}

.feature__list {
  display: flex;
  flex-wrap: wrap;
}

.feature__item {
  margin-right: 30px;
  flex-basis: calc((100% - 90px) / 4);
}

.benefits {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 30px;
  background-color: #f5f4fa;
  width: 270px;
  height: 120px;
}

.feature__item:last-child {
  margin-right: 0;
}

.benefits__title {
  color: var(--title-text-color);
  font-weight: 700;
  font-size: 14px;
  line-height: 1.14;
  letter-spacing: 0.03em;
  text-transform: uppercase;
  margin-top: 0;
  margin-bottom: 10px;
}

.benefits__text {
  font-size: 14px;
  line-height: 1.71;
  letter-spacing: 0.03em;
}

/*-------------чем мы занимаемся & наша команда--------------------*/
.work {
  padding-top: 0;
}
.work-title {
  margin-bottom: 50px;
  color: var(--title-text-color);
  font-weight: 700;
  font-size: 36px;
  line-height: 1.16;
  letter-spacing: 0.03em;
  text-align: center;
}

.work__list {
  display: flex;
  flex-wrap: wrap;
}
.work__item:not(:last-child) {
  margin-right: 30px;
}


.work-thumb {
  position: relative;
}

.work-thumb__text {
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 70px;

  font-weight: 700;
  font-size: 14px;
  line-height: 1.14;
  text-align: center;
  letter-spacing: 0.03em;
  text-transform: uppercase;

  color: var(--white-color);
  background-color: rgba(47, 48, 58, 0.8);
}

/*наша команда*/
.comand {
  background-color: #f5f4fa;
}

.comand__title {
  margin-bottom: 50px;
  color: var(--title-text-color);
  font-weight: 700;
  font-size: 36px;
  line-height: 1.16;
  letter-spacing: 0.03em;
  text-align: center;
}

.comand__list {
  display: flex;
  flex-wrap: wrap;
}

.comand__items {
  margin-right: 30px;
  background-color: var(--white-color);
  box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.12), 0px 1px 1px rgba(0, 0, 0, 0.14),
    0px 2px 1px rgba(0, 0, 0, 0.2);
  border-radius: 0px 0px 4px 4px;
}

.comand__items:last-child {
  margin-right: 0;
}

.avatar {
  padding: 30px 32px;
}

.avatar__title {
  margin-bottom: 10px;

  color: var(--title-text-color);
  font-weight: 500;
  font-size: 16px;
  line-height: 1.19;
  letter-spacing: 0.03em;

  text-align: center;
}

.avatar__text {
  margin-bottom: 16px;
  font-size: 16px;
  line-height: 1.19;
  letter-spacing: 0.03em;

  text-align: center;
}

.social {
  display: flex;
  padding: 0;
  margin: 0;
}

.social__item {
  margin-right: 10px;
}

.social__item:last-child {
  margin-right: 0;
}

.social__link {
  display: flex;
  justify-content: center;
  align-items: center;

  width: 44px;
  height: 44px;
  border-radius: 50%;
  color: var(--logo-color);

  transition: background-color 250ms var(--transition-timing-function),
    color 250ms var(--transition-timing-function);
}

.social__icon {
  fill: currentColor;
}

.social__link:hover,
.social__link:focus {
  background-color: var(--accent-color);
  color: var(--white-color);
}

/* ----------------Постоянные клиенты---------------- */
.clients {
  text-align: center;
}

.clients-title {
  margin-bottom: 50px;
  font-weight: 700;
  font-size: 36px;
  line-height: 42px;
  text-align: center;
  letter-spacing: 0.03em;
  color: var(--title-text-color);
}

/* ul */
.clients__list {
  display: flex;
  padding: 0;
  margin: 0;
}

.clients__item {
  margin-right: 30px;
}

.clients__item:last-child {
  margin-right: 0;
}

.clients__link {
  display: flex;
  justify-content: center;
  align-items: center;

  width: 170px;
  height: 92px;
  border: 1px solid var(--logo-color);
  border-radius: 4px;
  color: var(--logo-color);

  transition: color 250ms var(--transition-timing-function),
    border 250ms var(--transition-timing-function);
}

.clients__img {
  fill: currentColor;
}

.clients__link:hover,
.clients__link:focus {
  color: var(--accent-color);
  border: 1px solid var(--accent-color);
}

/*---------------footer---------------------------*/
.page-footer {
  padding: 60px 0;
  background-color: var(--section-color);
}

.footer {
  align-items: baseline;
  display: flex;
}

.wrapper {
  margin-right: 70px;
} 

.wrapper__logo {
  display: inline-block;
  margin-bottom: 20px;
  color: var(--white-color);
  font-family: Raleway;
  font-size: 26px;
  line-height: 1.19;
  letter-spacing: 0.03em;
}

.wrapper__icon {
  color: var(--accent-color);
}

.addres__link {
  width: 231px;
}

.addres__items {
  margin-bottom: 9px;
}

.addres__items:last-child {
  margin-bottom: 0px;
}

.addres__link {
  font-style: normal;
  color: var(--white-color);
  background-color: var(--section-color);
  font-size: 14px;
  line-height: 1.71;
  letter-spacing: 0.03em;
}

.addres__contacts {
  font-style: normal;
  color: rgba(255, 255, 255, 0.6);
  background-color: var(--section-color);
  font-size: 14px;
  line-height: 1.71;
  letter-spacing: 0.03em;

  transition: color 250ms var(--transition-timing-function);
}
}

.addres__contacts:hover,
.addres__contacts:focus {
  color: var(--accent-color);
}


.accede {
  margin-right: 93px;
}

.accede__title {
  font-weight: 700;
  font-size: 14px;
  line-height: 1.14;
  letter-spacing: 0.03em;
  text-transform: uppercase;
  color: #ffffff;
  margin-bottom: 20px;
}

.accede__list {
  display: flex;
  padding: 0;
  margin: 0;
  width: 206px;
}

.accede__item {
  margin-right: 10px;
}

.accede__item:last-child {
  margin-right: 0;
}

.accede__link {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 44px;
  height: 44px;
  border-radius: 50%;
  background-color: rgba(255, 255, 255, 0.1);
  color: var(--white-color);

  transition: background-color 250ms var(--transition-timing-function);
}

.accede__logo {
  fill: currentColor;
}

.accede__link:hover,
.accede__link:focus {
  background-color: var(--accent-color);
}

.subscribe__title {
  margin-bottom: 20px;
  font-weight: 700;
  font-size: 14px;
  line-height: 1.14;
  letter-spacing: 0.03em;
  text-transform: uppercase;

  color: #ffffff;
}

.subscribe-form {
  position: relative;
  display: flex;
  margin: 0 auto;
}

.form__field {
  position: relative;
  display: flex;
  flex-direction: column;
  width: 358px;
  height: 50px;
  margin-right: 10px;
}

  .form__input {
    margin: 0;
    padding: 15px;
    background-color: inherit;
    color: var(--white-color);

    border: 1px solid rgba(255, 255, 255, 0.3);
    box-sizing: border-box;
    filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.15));
    border-radius: 4px;

    transition: border-color 250ms var(--transition-timing-function),
    outline 250ms var(--transition-timing-function);
}

.form__input:hover,
.form__input:focus {
  border-color: rgba(255, 255, 255, 0.5);
  outline: none;
}

.form__input::placeholder {
  color: rgba(255, 255, 255, 0.3);

  transition: color 250ms var(--transition-timing-function);
}

.form__input:hover::placeholder,
.form__input:focus::placeholder {
  color: rgba(255, 255, 255, 0.5);
}

.form-btn {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: inherit;
  padding: 10px 30px;
  min-width: 200px;

  font-weight: 700;
  font-size: 16px;
  line-height: 1.88;
  letter-spacing: 0.06em;

  background-color: var(--accent-color);
  color: var(--white-color);
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15);
  border-radius: 4px;
  border-style: none;

  transition: background-color 250ms var(--transition-timing-function);
}

.form-btn:hover,
.form-btn:focus {
  background-color: var(--button-hover);
}

.form-btn__icon {
  fill: var(--white-color);
  margin-left: 10px;
}

/*Portfolio*/
/*buttons*/
.portfolio__title--visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  border: 0;
  padding: 0;
  white-space: nowrap;
  clip-path: inset(100%);
  clip: rect(0 0 0 0);
  overflow: hidden;
}

.filter {
  display: flex;
  justify-content: center;
  margin-bottom: 50px;
}

.filter__items {
  margin-right: 8px;
}

.filter__items:last-child {
  margin-right: 0;
}

.filter__btn {
  padding: 6px 22px;
  border-radius: 4px;
  border: transparent;

  background-color: var(--button-bgc);
  color: var(--title-text-color);
  cursor: pointer;
  font-family: inherit;
  font-weight: 500;
  font-size: 16px;
  line-height: 1.62;
  letter-spacing: 0.03em;

  text-align: center;

  transition: background-color 250ms var(--transition-timing-function),
    color 250ms var(--transition-timing-function),
    box-shadow 250ms var(--transition-timing-function);
}

.filter__btn:hover,
.filter__btn:focus {
  background-color: var(--accent-color);
  color: var(--white-color);
  box-shadow: 0px 3px 1px rgba(0, 0, 0, 0.1), 0px 1px 2px rgba(0, 0, 0, 0.08),
    0px 2px 2px rgba(0, 0, 0, 0.12);
}

.grid {
  display: flex;
  flex-wrap: wrap;
}

.grid__item {
  width: calc((100% - 60px) / 3);
  margin-right: 30px;
  margin-bottom: 30px;
}

.grid__link {
  display: block;

  transition: box-shadow 250ms var(--transition-timing-function);
}

.grid__link:hover,
.grid__link:focus {
  box-shadow: 0px 1px 1px rgba(0, 0, 0, 0.12), 0px 4px 4px rgba(0, 0, 0, 0.06),
    1px 4px 6px rgba(0, 0, 0, 0.16);
}

.grid__link:hover .thumb__text,
.grid__link:focus .thumb__text {
  transform: translate(0);
}

.grid__item:nth-child(3n) {
  margin-right: 0;
}

.grid__item:nth-last-child(-n + 3) {
  margin-bottom: 0;
}

.thumb {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.thumb__text {
  position: absolute;
  bottom: 0;
  right: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(33, 150, 243, 0.9);

  transform: translateY(100%);
  transition: transform 250ms var(--transition-timing-function);
}

.thumb__text > p {
  padding: 63px 24px;

  font-size: 18px;
  line-height: 1.56;
  letter-spacing: 0.03em;
  color: var(--white-color);
}

.aside {
  padding: 20px 24px;
  border-left: 1px solid #eeeeee;
  border-right: 1px solid #eeeeee;
  border-bottom: 1px solid #eeeeee;
}
.aside__items {
  margin-bottom: 4px;
  color: var(--title-text-color);
  font-weight: 700;
  font-size: 18px;
  line-height: 2;

  letter-spacing: 0.06em;
}

.aside__text {
  font-size: 16px;
  line-height: 1.87;
  letter-spacing: 0.03em;
  color: var(--primary-text-color);
}