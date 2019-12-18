---
title: 보고서 페이지 도구 설명을 사용하여 시각적 개체 확장
description: 보고서 페이지 도구 설명 사용 가이드
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/24/2019
ms.author: v-pemyer
ms.openlocfilehash: b7256a04ccdca107ef0cd8e24af8b3170a3d68cc
ms.sourcegitcommit: e492895259aa39960063f9b337a144a60c20125a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74834727"
---
# <a name="extending-visuals-with-report-page-tooltips"></a>보고서 페이지 도구 설명을 사용하여 시각적 개체 확장

이 문서에서는 독자가 Power BI 보고서를 설계하는 보고서 작성자라고 가정하고, [보고서 페이지 도구 설명](../desktop-tooltips.md)을 만들기 위한 제안 및 권장 사항을 제공합니다.

## <a name="suggestions"></a>제안

보고서 페이지 도구 설명은 보고서 사용자의 경험을 향상시킬 수 있습니다. 페이지 도구 설명을 사용하면 보고서 사용자가 빠르고 효율적으로 시각적 개체에 대한 깊이 있는 인사이트를 파악할 수 있습니다. 도구 설명은 각종 보고서 개체에 연동될 수 있습니다.

- **시각적 개체:** 개별 시각적 개체별로 어느 시각적 개체에서 페이지 도구 설명을 표시할지 설정할 수 있습니다. 각 시각적 개체별로 도구 설명을 표시하지 않거나 해당 시각적 개체의 도구 설명(시각적 개체 필드 창에서 설정)을 표시하거나 특정 페이지 도구 설명을 표시할 수 있습니다.
- **시각적 개체 헤더:** 특정 시각적 개체에 페이지 도구 설명이 표시되도록 구성할 수 있습니다. 보고서 사용자가 시각적 개체 헤더 아이콘에 커서를 올리면 페이지 도구 설명이 표시됩니다. 사용자에게 이 아이콘의 사용법을 안내하는 것을 잊지 마세요.

> [!NOTE]
> 보고서 시각적 개체는 도구 설명 페이지 필터가 시각적 개체의 디자인과 호환되는 경우에만 페이지 도구 설명을 보여 줄 수 있습니다. 예를 들어, _제품_으로 그룹화되는 시각적 개체는 _제품_으로 필터링되는 도구 설명 페이지와 호환됩니다.
>
> 페이지 도구 설명에서는 대화형 작업이 지원되지 않습니다. 보고서 사용자가 대화형으로 작업하도록 하려면 대신 [드릴스루 페이지](../desktop-drillthrough.md)를 만드세요.
>
> 사용자 지정 시각적 개체는 페이지 도구 설명을 지원하지 않습니다.

다음은 제안하는 몇 가지 디자인 시나리오입니다.

- [다른 관점](#different-perspective)
- [세부 정보 추가](#add-detail)
- [도움말 추가](#add-help)

### <a name="different-perspective"></a>다른 관점

페이지 도구 설명은 동일한 데이터를 원본 시각적 개체로 시각화할 수 있습니다. 동일한 시각적 개체를 사용하여 그룹을 피벗하거나 다른 시각적 개체 유형을 사용하여 이렇게 할 수 있습니다. 페이지 도구 설명은 원본 시각적 개체에 적용된 필터와 다른 필터를 적용할 수도 있습니다.

다음 예에서는 보고서 사용자가 **EnabledUsers** 값에 커서를 올리면 무슨 일이 일어나는지 보여 줍니다. 값의 필터 컨텍스트는 2018년 11월 Yammer입니다.

![행렬 시각적 개체가 행에서 연도와 월로 그룹화된 값 그리드를 표시하고 있습니다. 보고서 사용자가 커서를 단일 값 위에 올렸습니다. 페이지 도구 설명이 나타났습니다.](media/report-page-tooltips/suggestion-different-perspective.png)

페이지 도구 설명이 표시되었습니다. 도구 설명은 다른 데이터 시각적 개체(꺾은선형 및 묶은 세로 막대형 차트)를 표시하고 대비되는 시간 필터를 적용합니다. 데이터 요소의 필터 컨텍스트는 2018년 11월이지만 페이지 도구 설명은 _월로 이루어진 1년치_ 추세를 표시하고 있는 것을 알 수 있습니다.

### <a name="add-detail"></a>세부 정보 추가

페이지 도구 설명은 추가적인 세부 정보를 표시하여 컨텍스트를 더할 수 있습니다.

다음 예에서는 보고서 사용자가 우편 번호 98022의 **Average of Violation Points**(위반 요소 평균) 값에 커서를 올리면 무슨 일이 일어나는지 보여 줍니다.

![값 그리드를 표시하는 테이블입니다. 이 테이블에는 열 3개가 있습니다. 페이지 도구 설명이 나타났습니다.](media/report-page-tooltips/suggestion-add-details.png)

페이지 도구 설명이 표시되었습니다. 우편 번호 98022에 대한 특정 특성과 통계가 표시되었습니다.

### <a name="add-help"></a>도움말 추가

시각적 개체 헤더에서 페이지 도구 설명을 표시하도록 구성할 수 있습니다. 서식 있는 텍스트 상자를 사용하여 페이지 도구 설명에 도움말 콘텐츠를 추가할 수 있습니다. 이미지와 도형을 추가하는 것도 가능합니다.

단추, 이미지, 텍스트 상자 및 도형도 시각적 개체 헤더 페이지 도구 설명을 표시할 수 있습니다.

다음 예에서는 보고서 사용자가 시각적 개체 헤더 아이콘에 커서를 올리면 무슨 일이 일어나는지 보여 줍니다.

![보고서 사용자가 시각적 개체 헤더 아이콘(물음표 아이콘) 위에 커서를 올렸습니다. 서식 있는 도구 설명이 나타났습니다.](media/report-page-tooltips/suggestion-add-help.png)

페이지 도구 설명이 표시되었습니다. 시각적 개체가 표시하는 측정값을 설명하는 서식 있는 텍스트가 표시되었습니다. 도구 설명에는 도형(선)도 포함되어 있습니다.

## <a name="recommendations"></a>권장 사항

보고서를 디자인할 때는 다음과 같은 방식을 따르는 것이 권장됩니다.

- **페이지 크기:** 페이지 도구 설명은 작은 크기로 구성하세요. 기본 제공되는 **도구 설명** 옵션(너비 320픽셀, 높이 240픽셀)을 사용하거나 사용자 지정 크기를 설정할 수 있습니다. 페이지 크기를 너무 크게 설정하면 원본 페이지에서 시각적 개체를 가릴 수 있습니다.
- **페이지 보기:** 보고서 디자이너에서 페이지 보기를 **실제 크기**로 설정하세요(페이지 보기의 기본값은 **페이지에 맞추기**입니다). 이렇게 하면 페이지 도구 설명을 디자인할 때 실제 크기로 볼 수 있습니다.
- **스타일:** 페이지 도구 설명에 보고서와 동일한 테마와 스타일을 사용하는 것이 좋습니다. 이렇게 하면 사용자가 페이지 도구 설명을 보고 보고서와의 일관성을 느낄 수 있습니다. 또는 도구 설명에 보고서와 보완되는 스타일을 사용하고, 이 스타일을 모든 페이지 도구 설명에 적용하는 것도 좋습니다.
- **도구 설명 필터:** 페이지 도구 설명을 디자인할 때 실제와 동일한 결과를 미리 보기로 볼 수 있도록 페이지 도구 설명에 필터를 할당하세요. 보고서를 게시하기 전에 필터를 제거하는 것도 잊지 마세요.
- **페이지 표시 유형:** 도구 설명 페이지는 항상 숨기세요. 사용자가 곧바로 도구 설명 페이지로 이동할 수 없어야 합니다.

## <a name="next-steps"></a>다음 단계

이 문서와 관련된 보다 자세한 내용을 알아보려면 다음 리소스를 참조하세요.

- [Power BI Desktop의 보고서 페이지에 기반한 도구 설명 만들기](../desktop-tooltips.md)
- [Power BI Desktop에서 도구 설명 사용자 지정](../desktop-custom-tooltips.md)
- Guy in a cube 비디오: [Power BI report page tooltip - How to create one in Power BI Desktop](https://www.youtube.com/watch?v=URTA7JZsAtw)(Power BI 보고서 페이지 도구 설명 - Power BI Desktop에서 페이지 도구 설명을 만드는 방법)
- 궁금한 점이 더 있나요? [Power BI 커뮤니티에 질문합니다.](https://community.powerbi.com/)