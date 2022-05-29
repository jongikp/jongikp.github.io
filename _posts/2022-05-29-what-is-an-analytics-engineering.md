---
layout: post
title: "데이터잡부, 근데 이제 Analytics Engineering을 곁들인"
categories: [Analytics Engineering]
tags: [글또]
toc: false
comments: true
---
# 시작하며,
![data_stack.png](https://miro.medium.com/max/1400/1*VME7n7__zjHBy1s-Y3TAHA.png)
먼저 작성했던 글인 [포지션이라는 틀에서 벗어나기](https://jongikp.github.io/%EB%82%98%EB%8A%94%20%EC%9D%B8%EA%B0%84%20%ED%8F%89%EC%96%91%EB%83%89%EB%A9%B4%EC%9D%B4%EB%8B%A4/2022/04/15/%ED%8F%AC%EC%A7%80%EC%85%98%EC%97%90%EC%84%9C-%EB%B2%97%EC%96%B4%EB%82%98%EA%B8%B0.html) 에도 적었듯이 데이터 관련 포지션이 해가 바뀔 수로 세분화가 되어 새로운 직군들이 나타나고 있습니다.
그렇기 때문에 굳이 직군명으로 인해 제 자신의 업무적 boundary가 생기는 것을 피하고자 `동료들이 데이터를 쉽게 활용할 수 있는 환경을 만드는 사람` 이라는 비전을 바탕으로 살고 있습니다.

그럼에도 불구하고 저의 직무적 비전과 매우 유사하다고 느껴지는 새로운 직무 영역(`Analytics Engineering`)이 나타나서 요즘 매우 관심있게 찾아보고 있습니다.
이번 포스팅은 **Analytics Engineering**에 대해 소개한 해외 아티클들의 일부를 발췌하고 종합적으로 저의 생각을 섞어서 해당 직무에 대해서 정리해보는 글을 작성해보려고 합니다.

# 알아보자, Analytics Engineering?
클라우드 기반 데이터 웨어하우스, 데이터 파이프라인 서비스, BI Tool들에 대한 접근성 및 사용성이 매우 편해지고 좋아지는 엄청난 변화가 생기면서 
이로 인해 데이터팀에 소속되지 않은 구성원들이 데이터 활용 능력만 기르면 누구나 쉽게 데이터를 기반으로 의사결정을 할 수 있게 되었습니다.

따라서 과거의 데이터팀은 데이터 수집 ~ 분석 까지의 모든 영역을 관장했다면, 현대의 데이터팀은 과거의 역할뿐만 아니라 누구나 데이터를 활용할 수 있는 환경을 만들기 위해 보다 더 정확하고 잘 정의된 데이터를 제공해야하는 역할 또한 수행해야합니다.
그러한 새로운 임무를 수행하기 위해 Analytics Engineering 영역이 발생하게 되었다고 합니다.

![dbt_rnr.png](https://www.getdbt.com/ui/img/guides/analytics-engineering/analytics-engineer-role.png)

## Perspective
Analytics Engineering의 직무적 관점은 데이터를 활용한 인사이트 도출 또는 의사결정의 영역보다 데이터 사용자들이 의사결정 또는 데이터에 대한 활용을 더 빠르고 잘할 수 있도록 하는 것에 관심을 갖습니다.
* 비즈니스 질문에 답을 할 수 있는 단일 테이블을 구축하는 것
* 데이터 테이블에 대해 가능한 가장 명확하게 명명하는 규칙
* 비즈니스 사용자가 데이터에 문제가 발생했을 때 알림을 줄 수 있는 방법
* 분석가나 다른 비즈니스 사용자에게 구축한 테이블을 빠르게 사용할 수 있도록 해주는 것
* 생성된 데이터의 품질을 개선하는 방법

## Responsibility
Analytics Engineering은 Data Analysis와 Data Engineering 사이에 있습니다.  
따라서 두 영역의 교차점에서 각 영역의 역할을 지원하기 위해 노력하며 분석 관련 작업을 보다 효과적으로 수행하기 위해 조직 차원에서 데이터를 더 잘 사용할 수 있도록 책임을 갖습니다.
* 데이터 엔지니어가 수집한 데이터에 대한 정화 작업 진행 (Data Hygiene)
* 데이터를 의미 있는 방식으로 구성 및 변환하고 필요에 따라 추가 컨텍스트를 제공하여 분석할 준비 제공
* 데이터 엔지니어와 협력하여 프로세스를 간소화하여 프로세스 초기에 데이터를 더 명확하게 구축
* 데이터 세트 및 분석과 관련된 문서를 유지 관리하고 데이터 팀의 모든 사람이 동일한 언어와 정의를 사용하도록 관리
* 필요에 따라 분석 프로젝트의 개발 및 설계 지원
* 조직이 데이터 분석을 사용하여 시스템, 기업 및 프로세스를 개선할 수 있는 기회 발견
* 조직의 기술 팀과 협력하여 복잡한 데이터베이스 구축 및 유지 관리
* 여러 소스에서 수집된 데이터를 모델링하여 하나의 마트 테이블 생성
* 의사 결정에 사용할 보고서를 생성하기 위해 데이터 마이닝 및 데이터 시각화를 위한 도구, 알고리즘 및 프로세스 개발 및 사용
* 조직의 다른 구성원(비즈니스 분석가, 주요 이해 관계자)이 다양한 데이터 도구를 사용하고 데이터 팀의 다른 구성원과 의사 소통할 수 있도록 필요에 따라 교육

## Skill
따라서 Perspective 와 Responsibility 를 종합했을 때,  
Analytics Engineering에서 주로 사용되는 skill은 분석 + 소프트웨어 엔지니어링 관련된 기술 및 도구들이 포함됩니다.
* SQL
* Python
* Data Mining
* Data Modeling
* Data Visualization
* Data Tools (e.g. BigQuery, DBT, Snowflake, Redshift, ....)
* Communication

# 누구나 데이터를 잘 활용할 수 있는 환경 만들기
여러 아티클들에 따르면, Analytics Engineering은 Data Engineering 과 Data Analysis의 중간 영역이라고 소개하고 있습니다.
그러나 제가 생각하기에는 Analytics Engineering을 하는 관점과 책임만 같다면, 기술적 범위는 규정될 필요가 없다고 생각합니다.
Analytics Engineering은 `조직 차원에서 누구나 데이터를 잘 활용할 수 있는 환경` 을 만드는 것에 목표를 둔 영역이기 때문입니다. 
따라서 제가 일상에서 접근해보고 있는 Analytics Engineering은 다음과 같습니다.

## Perspective
* 비즈니스에 답을 찾아갈 수 있도록 마트 테이블을 구축하는 것
* 마트 테이블에 대해 가능한 가장 명확하게 명명하는 것
* 분석가나 데이터 사용자에게 구축한 마트 테이블을 잘 사용할 수 있도록 알려주는 것
* 생성된 데이터의 품질을 개선하고 관리하는 것
* 이벤트 로그에 대한 작성 및 개발 규칙을 만들어가는 것

## 현재의 Responsibility
![star-schema.png](https://cdn.holistics.io/guidebook/star-schema.png)
* 데이터 엔지니어와 협력하여 프로세스를 간소화하여 프로세스 초기에 데이터를 더 명확하게 구축
* 데이터 세트 및 분석과 관련된 문서를 유지 관리하고 데이터 팀의 모든 사람이 동일한 언어와 정의를 사용하도록 관리
* 데이터를 의미 있는 방식으로 구성 및 변환하고 필요에 따라 추가 컨텍스트를 제공하여 분석할 준비 제공
* 여러 소스에서 수집된 데이터를 모델링하여 하나의 마트 테이블 생성
* 조직이 데이터 분석을 사용하여 시스템, 기업 및 프로세스를 개선할 수 있는 기회 발견
* 조직의 기술 팀과 협력하여 복잡한 데이터베이스 구축 및 유지 관리

## 조만간 추가될 Responsibility
* 필요에 따라 분석 프로젝트의 개발 및 설계 지원
* 조직의 다른 구성원(비즈니스 분석가, 주요 이해 관계자)이 다양한 데이터 도구를 사용하고 데이터 팀의 다른 구성원과 의사 소통할 수 있도록 필요에 따라 교육
* Scientific Modeling 이 수행된 데이터를 생성하고 누구나 쓸 수 있도록 제공

# 마치며,
아티클을 읽고 생각을 해보았을 때, Analytics Engineering은 기술적인 것보다 관념적인 것이라고 느껴졌습니다.
이 쪽 영역에 대해 스스로 보다 발전시키기위해 어떠한 기술을 익혀야할까 의 고민보다 어떻게 접근해야할까 를 더 많이 생각해보았던 것 같습니다.
다행히도 Analytics Engineering에 대해 알아보면 알아볼수록 저의 직무적 비전과 너무 일치하여, 일상 안에서 관점적으로 접근해보는 것이 어렵지 않은 것 같습니다.
그 덕에 제가 가진 경험과 기술들을 활용해서 `조직 차원에서 누구나 데이터를 잘 활용할 수 있는 환경` 을 만들 수 있도록 시도할 수 있는 동기부여를 얻고 있는 것 같습니다.

그래도 앞으로 이어갈 포스팅에서는 Analytics Engineering을 보다 잘 수행할 수 있도록 하는 기술적인 것들에 대해서 작성해보려고 합니다.
읽어주셔서 감사하고 앞으로도 잘 부탁드립니다.

# Reference
* https://www.getdbt.com/what-is-analytics-engineering/
* https://www.northeastern.edu/graduate/blog/what-is-an-analytics-engineer/
* https://towardsdatascience.com/analytics-engineer-the-newest-data-career-role-b312a73d57d7
* https://towardsdatascience.com/analyst-2-0-3c10daf124c8
* https://www.holistics.io/books/setup-analytics/kimball-s-dimensional-data-modeling/
