# Troop Web Host Overrides
These override will force Troop Web Host's widget sizing/ margin limits with sections and widgets as well as other overrides over the main CSS of the entire page effecting the nav menu, page-title, scrollbar, etc.
## Section Overrides (1) - Oct 17th 2021

### 1) Create a full screen section (custom source code)
![](https://user-images.githubusercontent.com/57206061/137651364-eeccaec0-d2a5-4f9d-ae8e-6bd68318c93e.png)

Add this css to the source code of the section that you want to be the 100% width of the screen. Do this with <style>.
```
/*TWH CSS overrides*/
.new-row {margin: 0;}
/*.page-title {display: none;} //<- optional (removes page title)*/
.new-row text-center with-border {display: none;}

.container-fluid {
    padding-right: 0;
    padding-left: 0;
}

.h1, .h2, .h3, h1, h2, h3 {
/* margin-top already 20 px */
    margin-bottom: 20px;
}

.row {
    margin-right: 0;
    margin-left: 0;
}
/*TWH CSS overrides ^^*/
```
Then add a container div with a width of 999999px and then set the max-width to 100%. This will force the section to take up the real 100% width of the screen.
```
.cont {
  width: 999999px;
  max-width: 100%;
}
```
## CSS Site Overrides (3) - Oct 17th 2021
### 1) Overide page-title to create banner image on all pages
![](https://user-images.githubusercontent.com/57206061/137651070-2c3e6e32-13b1-41b1-b474-a74d29a37490.png)

Add this to your custom CSS file and then upload it under Menu > Site Configuration > Site Appearance then click on the CSS (Advanced) tab.
```
.page-title {
    margin: 0px;
    margin-bottom: 30px;
    padding: 40px;
    text-align: center;
    font-size: 35px;
    /*background-color: #4D9AFF;*/
    color: #fff;
    background-image: url('https://troopwebhost.blob.core.windows.net/troop677wildwood/Screenshot_2021-09-20_12.04.27_AM_202192014542713549.png');
    background-size: 100% auto;
    background-position: 65% 65%;
}
```
### 2) More Aesthetic Scrollbar
![](https://user-images.githubusercontent.com/57206061/137658917-dc2f8398-4cf6-4a30-8635-4d58912a9bcc.png)

Add this to your custom CSS file and then upload it under Menu > Site Configuration > Site Appearance then click on the CSS (Advanced) tab.
```
/* scrollbar */
::-webkit-scrollbar {
  position: relative;
  width: 1.25rem; /*<< width for vertical scrollbar*/
  height: 1.25rem; /*<< height for horzontal scrollbar */
  background-color: #fff;
}

::-webkit-scrollbar-thumb {
  border-radius: 1rem;
  -webkit-box-shadow: inset 0 0 6px rgba(129, 123, 123, 0.3);
  background-color: #8b928ea2;
}

::-webkit-scrollbar-thumb:hover {
  background-color: #7e8380;
}

::-webkit-scrollbar-thumb:active {
  background-color: #1D1D1F;
}
```
### 3) Redesigned Fixed Nav Menu Overrides
![](https://user-images.githubusercontent.com/57206061/137653280-d7d24c45-68fc-462e-b84e-daa828db8cc9.png)

Add this to your custom CSS file and then upload it under Menu > Site Configuration > Site Appearance then click on the CSS (Advanced) tab.


Some of the main updates are:
- Vertically centered text with more padding
- Fixed nav menu position (follows the top of the page on scroll)
- Gradual bolding on hover
- Overflow of the dropdown menu scrolls (with hidden scrollbars)
- Other small detail upgrades
```
/* resized header main body position fix */
body {
  padding-top: 4.5rem;
}

/* Nav stuff */
.table-striped > thead > tr {
  background-color: rgb(49, 133, 216);
  color: white;
}

.navicon {
  text-align: right;
  background-color: transparent;
  color: rgb(255, 255, 255);
  padding-top: 0.6%; /*0.7*/
  padding-left: 0%; 
  z-index: 1010;
}

.navtable {
  position: fixed;
/* TOP MENU COLOR CHANGE HERE*/
  background-color: rgb(49, 133, 216);
  color: #fff;
  height: 45px;
  top: 0px;
  z-index: 1000;
}

.navlink {
  position: relative;
  color: #fff;
/*MAIN PADDING */
  padding-top: 0.4rem;
  vertical-align: text-bottom;
}

.navlink > a {
  color: #fff;
  padding-top: 5%;
}

.navmenu {
/* top positioning lowered with margin-top */
  margin-top: 13px;
  width: 392px;
  left: -500px;
  z-index: 99999;
/* scroling properties */
  position: fixed;
  min-height: 0px;
  overflow: scroll;
  max-height: 95%;
  padding-bottom: 1px;
/* asthetic background changes */
  background: linear-gradient(90deg, #fff, 50%, transparent 50%);
}

.navmenu::-webkit-scrollbar {
  display: none;
}

.list-group {
  /* No need to set list-style: none; since .list-group-item is block level */
  margin-bottom: 0 !important;
}

.list-group-item {
  padding: 6px !important;
  padding-left: 15px !important; padding-right: 15px !important;
}

/* Bolding transitions */
.navlink a:hover,
.navlink a:focus,
.navlink:hover,
.navlink:focus {
  font-weight: normal; /* reset to normal (recalled to bold on hover somewhere else) */
  text-decoration: none;
  background-color: transparent;
  color: #fff;
  /* change 0 to 1 values to turn it off*/
    text-shadow:
    -0.3px -0.3px 0 rgb(255, 255, 255),
    0.3px -0.3px 0 rgb(255, 255, 255),
    -0.3px 0.3px 0 rgb(255, 255, 255),
    0.3px 0.3px 0 rgb(255, 255, 255);
    -webkit-transition: all .5s;
    -moz-transition: all .5s;
    -o-transition: all .5s;
    transition: all .5s;
}

/* Menu icon hover bolding */
.navicon:hover,
.navicon:focus {
  text-decoration: none;
  background-color: transparent;
  color: #fff;
    text-shadow:
    /*Menu bolding is good so left on*/
    -0.1px -0.1px 0 rgb(255, 255, 255),
    0.1px -0.1px 0 rgb(255, 255, 255),
    -0.1px 0.1px 0 rgb(255, 255, 255),
    0.1px 0.1px 0 rgb(255, 255, 255);
    -webkit-transition: all .5s;
    -moz-transition: all .5s;
    -o-transition: all .5s;
    transition: all .5s;
}

.navtools {
  z-index: 99999;
  margin-top: 13px;
}
/*End of nav stuff*/
```
