---
title: データ保護影響評価
description: このドキュメントには、データ管理者に対し、DPIA が必要であるかどうかを判断し、必要な場合には DPIA に含める詳細情報を決定する上で役立つ情報が記載されています。
keywords: データ保護影響評価、DPIA、Dynamics 365、Microsoft プロフェッショナル サービス、Microsoft 365、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 7c4e66988c57754324fbc18de95e97d409ab0a53
ms.sourcegitcommit: c201f5cc13d501e5207ebad166e42f90260af0c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2019
ms.locfileid: "35078917"
---
# <a name="data-protection-impact-assessment-for-the-gdpr"></a>GDPR のデータ保護影響評価

一般データ保護規則 (GDPR) では、欧州連合 (EU) 内の人々に商品やサービスを提供する、または EU 居住者向けのデータの収集と分析を実行する会社に対して、新しい規則を導入します。GDPR は、個人やその企業がどの場所にあるかに関係なく適用されます。 詳細については、「[GDPR 概要トピック](gdpr.md)」を参照してください。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrOQE] 

このドキュメントでは、Microsoft の製品とサービスを使用する際の GDPR に基づくデータ保護影響評価 (DPIA) に関する情報を提供します。

## <a name="terminology"></a>用語

このドキュメントで使用されている GDPR 用語の役に立つ定義:

- *データ コントローラー (コントローラー)*: 法人、公的機関、団体、その他の組織。単独または他者と協力して、個人データの処理の目的と方法を決定します。  
- *個人データ*と*データ主体*: 特定されたまたは特定可能な自然人 (データ主体) に関連するあらゆる情報。特定可能な自然人とは、直接または間接的に特定することができる者のことです。  
- *処理者:* コントローラーに代わって個人データを処理する自然人または法人、公的機関、団体、その他の組織。  
- *顧客データ*: ビジネス運営における日々の業務で作成および保存されるデータ。

## <a name="what-is-a-dpia"></a>DPIA とは?

GDPR では、コントローラーは「自然人の権利と自由を危険にさらす可能性が高い」操作に関してデータ保護影響評価 (DPIA) を準備する必要があります。 DPIA の作成を必要とする Microsoft の製品とサービスに固有のものはありません。 ただし、Microsoft の製品とサービスは高度なカスタマイズが可能であるため、Microsoft の構成の詳細に応じて DPIA が必要になる場合があります。 Microsoft は、このような情報に関して制御することは一切なく、分析情報を得ることもほとんどありません。 お客様はデータ コントローラーとして、データの適切な使用を決定する必要があります。

## <a name="dpia-in-action"></a>実行中の DPIA

DPIA ガイダンスは、Office 365、Azure、Dynamics 365、Microsoft サポート/プロフェッショナル サービスに適用されます。 このガイダンスには、以下の考慮事項が含まれています。

1. **いつ DPIA が必要か?**: DPIA を完了するかどうかを検討する際には、以下のリスク要因に対処する必要があります。 その他の潜在的要因と詳細については、各ガイドラインの第 1 部を参照してください。  

    - 自動処理に基づく、データの体系的かつ広範囲な評価。  
    - 特殊なカテゴリのデータ (自然人を一意に識別する情報が明らかになるデータ)、または有罪判決や違反に関する個人データを対象とした大規模な処理。
    - 公開アクセス可能な地域での体系的な大規模監視。

    GDPR では次のように説明しています。「個人データの処理は、処理が個々の医師、他の医療専門家、または弁護士の患者または依頼主に関するものである場合、大規模な処理とはみなされない。 その場合、データ保護影響評価は必須ではない」。

2. **DPIA を完了するために何が必要か?**: DPIA では、想定された処理作業に関する具体的な情報を提供する必要があります。これは、このガイダンスの第 2 部で詳細に説明します。 この情報には、次のものがあります。

    - DPIA の目的に関するデータ処理作業の必要性および比例性の評価。  
    - 自然人の権利および自由に関するリスクの評価。
    - 個人データを確実に保護し、GDPR 準拠を実証するためのセーフガード、セキュリティ対策、メカニズムを含む、リスクに対処するための想定された対策。
    - 処理の目的  
    - 処理される個人データのカテゴリ  
    - データ保持  
    - 個人データの保存場所と移転  
    - 第三者の副処理者とのデータの共有  
    - 独立した第三者とのデータの共有  
    - データ主体の権利

## <a name="additional-considerations"></a>その他の考慮事項

Microsoft 実装に関連する可能性がある具体的な詳細情報については、以下を参照してください。

- [Office 365](gdpr-dpia-office365.md): このドキュメントは、Exchange Online、SharePoint Online、Yammer、Skype for Business、Power BI などの Office 365 のアプリケーションとサービスに適用されます。ただし、これに限定されるものではありません。 詳細については、表 [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) と [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia) を参照してください。  
- [Azure](gdpr-dpia-azure.md): Microsoft Azure の使用に関しての DPIA の必要性および内容を判断するにあたり、お客様にはプライバシー責任者または弁護士と連携することをお勧めします。  
- [Dynamics 365](gdpr-dpia-dynamics.md): DPIA の内容は、使用している Dynamics 365 ツールによって異なる場合があります。 詳細については、「[パート 2 - DPIA の内容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia)」を参照してください。
- [Microsoft サポート/プロフェッショナル サービス](gdpr-dpia-prof-services.md): プロフェッショナル サービスでは、特定のルーチンまたは自動データ処理は行われません。また、特別なカテゴリを処理したり、パブリックにアクセス可能なデータの監視を促進または要求するタスクを実行したりすることも想定されていません。 詳細については、「[パート 1 - DPIA が必要であるかどうかの判断](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed)」を参照してください。 コントローラーは、コントローラーによる特定の実装およびプロフェッショナル サービスの使用において、上記の DPIA 要素を他のすべての関連要因とともに考慮する必要があります。 プロフェッショナル サービス情報については、「[パート 2 - DPIA の内容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia)」を参照してください。

## <a name="learn-more"></a>詳細情報

- [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
