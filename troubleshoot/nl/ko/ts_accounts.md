---

copyright:
  years: 2015, 2016

---

{:tsSymptoms: .tsSymptoms} 
{:tsCauses: .tsCauses} 
{:tsResolve: .tsResolve} 
{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}
{:codeblock: .codeblock} 





# 계정 관리 문제점 해결
{: #managingaccounts}

마지막 업데이트 날짜: 2016년 8월 18일
{: .last-updated}

계정을 관리할 때 여러 앱이 동일한 도메인 이름을 공유하거나 관리자가 일부 조직을 볼 수 없는 것과 같은 문제점이 발생할 수 있습니다. 그러나 대부분의 경우
몇 가지 간단한 단계를 수행하여 이러한 문제점에서 복구할 수 있습니다. 
{:shortdesc}


## 계정이 비활성화됨
{: #ts_accnt_inactive}

계정이 비활성 상태일 경우 {{site.data.keyword.Bluemix_notm}}에서 앱을 작성할 수 없습니다. 이 문제점을 해결하려면 지원 팀에 문의해야 합니다.



{{site.data.keyword.Bluemix_notm}}에서 앱을 작성하려고 할 때 다음과 같은 오류 메시지가 표시됩니다.
{: tsSymptoms} 

`BXNUI0096E: The app wasn't created. Your account is inactive because it was canceled or suspended.`


계정이 취소되었거나 일시중단된 경우 {{site.data.keyword.Bluemix_notm}} 계정의 상태가 비활성화됩니다.
{: tsCauses}

 

계정을 다시 활성화하려면 [{{site.data.keyword.Bluemix_notm}} 지원 센터](http://ibm.biz/bluemixsupport.com){: new_window}에 문의하십시오. 이메일에 다음 정보를 포함해야 합니다.
{: tsResolve}

  * {{site.data.keyword.Bluemix_notm}}에 로그인하는 데 사용하는 IBM ID입니다.
  * 작성하는 앱이 속할 조직의 이름. 이 정보는 지원 팀이 조직 내 사용자에게 올바른 역할 또는 멤버십이 지정되었는지 판별하는 데 도움이 됩니다.



## 현재 조직과 연관된 영역이 없음
{: #ts_no_space}

영역이 현재 조직과 연관되어 있지 않은 경우
애플리케이션을 작성할 수 없습니다.



{{site.data.keyword.Bluemix_notm}}에서 앱을 작성하려고 할 때 다음과 같은 오류 메시지가 표시됩니다.
{: tsSymptoms} 


`BXNUI0097E: Before you can add an app, at least one space must be associated with your organization and region. On the Dashboard, click Create a Space. When the space is created, try again.`



{{site.data.keyword.Bluemix_notm}}의 앱은 조직 아래의 영역 내에 작성되어야 합니다.
{: tsCauses} 

 

영역을 작성하려면 다음 방법 중 하나를 사용하십시오. 
{: tsResolve}
 
  * {{site.data.keyword.Bluemix_notm}} 대시보드에서 영역을 작성할 조직을 선택한 다음 **영역 작성**을 클릭하십시오.
  * cf 명령행 인터페이스에서 `cf create-space <space_name> -o <organization_name>`을 입력하십시오.
  
  
  
  
## 앱이 동일한 도메인 이름을 공유함
{: #ts_domain_diff}

{{site.data.keyword.Bluemix_notm}}에서
여러 애플리케이션이 동일한 URL을 공유할 수 있습니다.

 

이 문제점은 한 영역 내의 서로 다른 애플리케이션에 대해 동일한 URL 라우트를 지정한 경우에 발생할 수 있습니다.
{: tsCauses}

예를 들어 myApp1 애플리케이션을 {{site.data.keyword.Bluemix_notm}}로 푸시하고 도메인을 "mynewapp.stage1.mybluemix.net"으로 설정하십시오. 그런 다음 다른 myApp2 애플리케이션을 동일한 영역으로 푸시하고 URL 라우트 중 하나를 "mynewapp.stage1.mybluemix.net"으로 설정하십시오. 이제 해당 라우트가 두 애플리케이션 모두에 맵핑되었습니다.

 

이는 {{site.data.keyword.Bluemix_notm}}의 지원되는 동작이므로 이 동작을 사용하여 애플리케이션 업그레이드 시 무중단을 실현할 수 있습니다. 자세한 정보는 Blue-Green 배치를 참조하십시오.
{: tsResolve}
  
	
	
<!-- begin STAGING ONLY --> 
	
	
## 관리자는 {{site.data.keyword.Bluemix_notm}} 사용자 인터페이스를 사용하여 모든 조직을 볼 수 없음
{: #ts_ui_org}

관리자는 {{site.data.keyword.Bluemix_notm}} 사용자 인터페이스를 사용할 때 모든 조직을 표시하여 관리할 수 없습니다. 관리자가 속한 조직만 표시하고 관리할 수 있습니다. 

 

관리자는 {{site.data.keyword.Bluemix_notm}} 사용자 인터페이스를 사용하여 모든 조직을 볼 수 없습니다.
{: tsSymptoms}

 

이는 {{site.data.keyword.Bluemix_notm}} 사용자 인터페이스의 제한사항입니다.
{: tsCauses}

 

cf 명령행 인터페이스에서 `cf orgs`, `cf create-org`, `cf delete-org`와 같은 명령을 사용하여 모든 조직을 관리할 수 있습니다. cf 명령의 전체 목록을 보려면 `cf help`를 입력하십시오.
{: tsResolve}
	
<!-- end STAGING ONLY -->




## 신용카드를 추가할 수 없음
{: #ts_addcc}

평가판 계정을 종량과금제 계정으로 변환하기 위해 신용카드 정보를 제출할 수 없습니다.

 

신용카드 추가 페이지의 제출 단추가 비활성화되어 있습니다.
{: tsSymptoms}

 

이 문제점은 신용카드 추가 페이지에 정보가 올바르게 채워지지 않은 경우에 발생합니다.
{: tsCauses}

 

이 문제점을 해결하려면 다음 단계를 수행하십시오.
{: tsResolve}

  1. 신용카드 추가 페이지에서 연락처 정보, 연락처 주소, 청구 주소 섹션에 있는 모든 필수 필드에 정보를 입력하십시오.
  2. **IBM 이용 약관을 읽고 동의함**을 선택한 다음 **제출**을 클릭하십시오. **지불 방법** 섹션이 표시됩니다.
  3. 신용카드 번호, 카드 만기 날짜 및 카드 상의 보안 코드를 입력하십시오. 그런 다음 **제출**을 클릭하십시오.


