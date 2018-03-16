---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: "page"
title: "프로필"
icon: fa-black-tie
order: 2
auto-header: none
description: devbobos의 현재 모습입니다, 계속해서 배워 나가려고 합니다.
---
<style>
.aboutmecontainer {
    position: relative;
}

.aboutmebottomleft {
    position: absolute;
    bottom: -24px;
    left: 8px;
}
.progress {
  overflow: hidden;
  height: 11px;
  background-color: #f5f5f5;
  border-radius: 4px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  vertical-align: middle;
  margin-top: 5.5px;
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 12px;
  color: #fff;
  text-align: center;
  background-color: #549EB4;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.about-table-item {
  margin-bottom: 0px;
  vertical-align: top;
  padding: 0em 1em 0.5em 1em;
}
@media (max-width:360px){
  .about-table {
    font-size: 10px;
  }
  .progress {
      height: 10px;
      margin-top: 5px;
  }
  .progress-bar {
    font-size: 10px;
    line-height: 10px;
  }
}
@media (min-width:360px) and (max-width:480px){
  .about-table {
  font-size:12px;
  }
  .progress {
      height: 12px;
      margin-top: 6px;
  }
  .progress-bar {
    font-size: 12px;
    line-height: 12px;
  }
}
@media (min-width:480px) and (max-width:640px){
  .about-table {
  font-size:14px;
  }
  .progress {
    height: 14px;
    margin-top: 7px;
  }
  .progress-bar {
    font-size: 14px;
    line-height: 14px;
  }
}
@media (min-width:640px){
  .about-table {
  font-size:20px;
  }
  .progress {
    height: 20px;
    margin-top: 10px;
  }
  .progress-bar {
    font-size: 20px;
    line-height: 20px;
  }
}
</style>
<div class="aboutmecontainer">
  <img src="assets/images/site/pic08.jpg" alt="portrait" style="width: 100%; height: auto;">
  <div class="aboutmebottomleft">
    <h2 style="text-align: left; color: white; font-weight: 600;">손보광</h2>
    <p style="text-align: left; color: white;">Mobile App Developer</p>
  </div>
</div>
<br>
## 학력사항
<div class="table-wrapper">
  <table>
    <tr>
      <td><p>2007.03 ~ 2010.02</p></td>
      <td colspan="2"><p><strong>선린인터넷고등학교</strong> 정보통신과 졸업</p></td>
    </tr>
    <tr>
      <td><p>2007.03 ~ 2017.08</p></td>
      <td colspan="2"><p><strong>한국외국어대학교</strong> 디지털정보공학과 졸업</p></td>
    </tr>
  </table>
</div>
<hr>
<br>
## 개발경험
<div class="table-wrapper">
  <table>
    <tr>
      <td><p>2015.03 ~ 2015.06</p></td>
      <td colspan="2"><p><strong>한국외국어대학교</strong> 인지적 착시 게임 개발 (Unity)</p></td>
    </tr>
    <tr>
      <td><p>2015.11 ~ 2016.07</p></td>
      <td colspan="2"><p><strong>Delimon</strong> 프론트엔드 개발 (Laravel)</p></td>
    </tr>
    <tr>
      <td><p>2016.07 ~ 현재</p></td>
      <td colspan="2">
        <strong>유수소프트</strong>
        <ul>
          <li>기획 및 Android, iOS 개발</li>
          <li>Server 및 Databse 설계</li>
        </ul>
      </td>
    </tr>
  </table>
</div>
<hr>
<br>
## 대외활동
<div class="table-wrapper">
  <table>
    <tr>
      <td><p>2015.07 ~ 2015.12</p></td>
      <td colspan="2">
        <strong>SK T아카데미 교육 이수</strong>
        <ul>
          <li>Objective C기초</li>
          <li>iPhone Application 개발 기초</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><p>2014.12 ~ 2015.01</p></td>
      <td colspan="2">
        <strong>KOSTA 교육 이수</strong>
        <ul>
          <li>객체지향 프로그래밍</li>
          <li>Backend (Servlet, JSP, MyBatis, Spring)</li>
          <li>Frontend (HTML, CSS, Javascript, AJAX)</li>
          <li>Android 개발</li>
        </ul>
      </td>
    </tr>
  </table>
</div>
<hr>
<br>
## 개발능력
<div class="table-wrapper">
  <table class="about-table">
    <tbody>
      <tr>
        <td></td>
        <td>N/A</td>
        <td>Experienced</td>
        <td>Familiar</td>
        <td>Expert</td>
      </tr>
      <tr>
        <td class="about-table-item"><p>PHP</p></td>
        <td colspan="4">
          <div class="progress">
              <div class="progress-bar" role="progressbar" aria-valuenow="40" aria-valuemin="0" aria-valuemax="100" style="width: 40%">
                  <span class="sr-only">80% Complete (success)</span>
              </div>
          </div>
        </td>
      </tr>
      <tr>
        <td class="about-table-item"><p>HTML</p></td>
        <td colspan="4" >
          <div class="progress">
              <div class="progress-bar" role="progressbar" aria-valuenow="80" aria-valuemin="0" aria-valuemax="100" style="width: 80%">
                  <span class="sr-only">80% Complete (success)</span>
              </div>
          </div>
        </td>
      </tr>
      <tr>
        <td class="about-table-item"><p>CSS</p></td>
        <td colspan="4" >
          <div class="progress">
              <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100" style="width: 60%">
                  <span class="sr-only">80% Complete (success)</span>
              </div>
          </div>
        </td>
      </tr>
      <tr>
        <td class="about-table-item"><p>Javascript</p></td>
        <td colspan="4" >
          <div class="progress">
              <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100" style="width: 60%">
                  <span class="sr-only">80% Complete (success)</span>
              </div>
          </div>
        </td>
      </tr>
      <tr>
        <td class="about-table-item"><p>C/C++</p></td>
        <td colspan="4" >
          <div class="progress">
              <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100" style="width: 60%">
                  <span class="sr-only">80% Complete (success)</span>
              </div>
          </div>
        </td>
      </tr>
      <tr>
        <td class="about-table-item"><p>Java</p></td>
        <td colspan="4" >
          <div class="progress">
              <div class="progress-bar" role="progressbar" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100" style="width: 100%">
                  <span class="sr-only">80% Complete (success)</span>
              </div>
          </div>
        </td>
      </tr>
      <tr>
        <td class="about-table-item"><p>Android</p></td>
        <td colspan="4" >
          <div class="progress">
              <div class="progress-bar" role="progressbar" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100" style="width: 100%">
                  <span class="sr-only">80% Complete (success)</span>
              </div>
          </div>
        </td>
      </tr>
      <tr>
        <td class="about-table-item"><p>Objective C</p></td>
        <td colspan="4" >
          <div class="progress">
              <div class="progress-bar" role="progressbar" aria-valuenow="80" aria-valuemin="0" aria-valuemax="100" style="width: 80%">
                  <span class="sr-only">80% Complete (success)</span>
              </div>
          </div>
        </td>
      </tr>
      <tr>
        <td class="about-table-item"><p>Swift</p></td>
        <td colspan="4" >
          <div class="progress">
              <div class="progress-bar" role="progressbar" aria-valuenow="40" aria-valuemin="0" aria-valuemax="100" style="width: 40%">
                  <span class="sr-only">80% Complete (success)</span>
              </div>
          </div>
        </td>
      </tr>
    </tbody>
  </table>
</div>
<hr>
<br>
## Contact
<form method="post" action="https://formspree.io/{{ site.email }}">
  <div class="row">
    <div class="6u 12u$(mobile)"><input type="text" name="name" placeholder="Name" /></div>
    <div class="6u$ 12u$(mobile)"><input type="text" name="email" placeholder="Email" /></div>
    <div class="12u$">
      <textarea name="message" placeholder="Message"></textarea>
    </div>
    <div class="12u$">
      <input type="submit" value="Send Message" />
    </div>
  </div>
</form>
