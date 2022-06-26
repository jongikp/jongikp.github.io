---
layout: post
title: "알아보자, DBT"
categories: [Analytics Engineering]
tags: [글또]
toc: true
comments: true
---
## 시작하며,
Analytics Engineering 에 관심을 가지게 되면서, [dbt(data build tool)](https://www.getdbt.com/product/what-is-dbt/) 라는 것을 알게되었습니다.   
이번에 쓰는 글은 dbt 라는 제품과 팀이 제시하는 관점과 그에 따른 저의 생각을 정리해보려고 합니다.

## dbt는 무엇이고 어떠한 관점을 갖고 있을까?
![dbt_workflow.jpg](https://www.getdbt.com/ui/img/png/analytics-engineering-dbt.png)   
[dbt 위키피디아](https://en.wikipedia.org/wiki/Data_build_tool) 에 따르면, dbt는 분석가와 엔지니어가 웨어하우스의 데이터를 보다 효과적으로 변환하는데 도움이 되는 오픈 소스 command line 도구라고 합니다.
dbt의 초기 버전을 통해 분석가는 소프트웨어 엔지니어링의 모범 사례에 따라 데이터 변환 프로세스에 기여할 수 있게 되었다고 합니다. 

dbt를 사용하게 되면 분석 엔지니어는 `select` 문을 작성을 통해 웨어하우스의 데이터를 변환할 수 있다고 합습니다.
dbt는 이러한 `select` 문을 `table` 과 `view` 로 변환하는 작업을 처리할 수 있도록 합니다.
즉, dbt는 ELT(Extract, Load, Transform) 프로세스에서 T 를 수행합니다.

**dbt의 목표는 분석가가 dbt 관점에 따라 소프트웨어 엔지니어처럼 작업할 수 있도록 하는 것이라고 합니다.**

dbt 블로그에 있는 [Building a Mature Analytics Workflow](https://www.getdbt.com/blog/building-a-mature-analytics-workflow/) 라는 아티클을 읽어보면,
dbt를 통해 Analytics Workflow를 정립하고 개선하고자 하는 것을 느낄 수 있습니다.

> Analytics teams have a workflow problem today. Too often, analysts operate in isolation, and this creates suboptimal outcomes. Knowledge is siloed.
> We too often rewrite analyses that a colleague had already written. We fail to grasp the nuances of datasets that we’re less familiar with.
> We differ in our calculations of a shared metric. As a result, organizations suffer from reduced decision speed and reduced decision quality.

본문에 따르면, 분석가는 너무 자주 고립이 되어 지식이 사일로화될 수 있고 이미 작성한 분석을 너무 자주 다시 작성하는 것 등등으로 인한 부분 때문에
분석팀의 workflow에는 문제점이 많이 발생한다고 합니다.   

따라서, 이러한 부분을 해소하고 성숙한 workflow를 구축하기 위해 그들이 제품에 담은 관점은 아래와 같습니다.
```
1. Analytics is collaborative
   - Version Control
   - Quality Assurance
   - Documentation
   - Modularity
2. Analytic code is an asset
   - Environments
   - Service level guarantees
   - Design for maintainability
3. Analytics workflows require automated tools
```

## 나의 생각은?
이 쪽 일을 하면서, dbt 팀이 말한대로 분석 관련 작업이 정말 자주 다시 작성되는 것을 많이 경험했습니다. 그러한 부분으로 인해 업무의 병목이 많이 생겼었던
기억이 다수 있습니다. 그로 인해, 내가 작성한 SQL 코드 혹은 분석을 위한 Python 코드를 어떻게 잘 관리할 수 있고 비슷한 요청 혹은 작업을 할 때 시간을
절약하고 작업할 수 있을까? 에 대해 상당히 고민을 많이 했었습니다.

그러한 고민을 해소시키려던 노력의 일환으로 분석용 코드 및 query를 github에 관리하려고 했었으나, 서비스 프로덕션 용이 아니면 제거해달라는 요청을 받아서 결국 로컬에서
스스로 versioning 을 하면서 관리했던 것이 기억이 납니다. 어떻게 보면, dbt가 제시하는 관점처럼 딱 명확하게 정리하고 실천하지는 않았지만 정말 비슷한 결로
로컬에서 관리하려고 했었던 것 같습니다.

그러나 이렇게 개인적으로 관리하는 부분은 사일로화를 가속화시키는 것 같아, 어떻게든 항상 위키를 활용하여 문서화를 하려고 했었습니다.
이렇게 관리하고 작업을 했지만, 팀 규모가 커질수록 모두가 같은 마음 그리고 같은 작업 속도가 아니기에 지식 및 공유의 불균형이 발생하고 그에 따른 피로감이 상당히 많이 발생었던 것 같습니다.

하지만 dbt를 활용한다면, 이러한 부분에서 느꼈던 것들과 불편했던 감정들이 해소될 것 같다는 생각이 들고 있습니다.
아직은 저도 실제로 활용하거나, 그 위에서 작업해본 적이 없어서 단정지을 수는 없지만, 그들이 제시하는 관점들이 제가 생각하는 것과 너무 일치하기에 분명 저에게 잘 맞을 것 같다는 확신이 듭니다.

따라서, 다음 포스팅에는 dbt를 하나하나씩 뜯어보면서 어떻게 작동되는 것이고 어떠한 기능들이 있는지 확인한 것들을 남겨보려고 합니다.

## 마치며,
dbt 팀이 말하는, **dbt의 목표는 분석가가 dbt 관점에 따라 소프트웨어 엔지니어처럼 작업할 수 있도록 하는 것이라고 합니다.** 매우 공감이 됩니다.  
Analytics Engineering이라는 이야기가 나온지 얼마 되지 않았는데, 이를 선도하는 팀이 dbt 팀이라는 것에 매우 놀라웠습니다.   
요즘 들어 정말 많이 느끼는 것은... 세상이 참 빠르게 변화하는 것 같다는 생각이 듭니다.
정말 은퇴하기 전까지 열심히 찾아보고 공부하고 시도해보고 흐름을 빠르게 잘 캐치해야하는 직종인 것은 확실한 것 같습니다.

우리 모두 화이팅 : )

## Reference
* <https://www.getdbt.com/analytics-engineering/start-here>
* <https://www.getdbt.com/blog/building-a-mature-analytics-workflow/>
