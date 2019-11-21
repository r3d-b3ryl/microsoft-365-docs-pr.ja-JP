---
title: 違反の通知
description: Microsoft サービスによる個人データ漏洩からの保護と、違反が発生した場合の Microsoft による対応とユーザーへの通知
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: e9d922b1ce537c85dbb24d884ca1560ad8e32459
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2019
ms.locfileid: "38749897"
---
# <a name="gdpr-breach-notification"></a>GDPR 違反の通知

一般データ保護規則 (GDPR) では、欧州連合 (EU) 内の人々に商品やサービスを提供する、または EU 居住者向けのデータの収集と分析を実行する会社に対して、新しい規則を導入します。GDPR は、個人やその企業がどの場所にあるかに関係なく適用されます。 詳細については、「[GDPR 概要トピック](gdpr.md)」を参照してください。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrZgG] 

このドキュメントは、Microsoft の製品とサービスの使用における、GDPR に基づく違反の通知の完了に関する情報を提供します。

## <a name="what-constitute-a-breach-of-personal-data-under-the-gdpr"></a>GDPR における個人データ侵害とは?

個人データは、個人に関連する情報のうち、直接的または間接的に個人を特定するために使用できるものを意味します。 個人データ侵害は、「送信、保存、またはその他の方法で処理される個人データの偶発的または違法の破損、損失、改変、不正漏洩、またはアクセスを引き起こすセキュリティ違反」です。

## <a name="terminology"></a>用語

このドキュメントで使用されている GDPR 用語の役に立つ定義:

- *データ コントローラー (コントローラー)*: 法人、公的機関、団体、その他の組織。単独または他者と協力して、個人データの処理の目的と方法を決定します。  
- *個人データ*と*データ主体*: 特定されたまたは特定可能な自然人 (データ主体) に関連するあらゆる情報。特定可能な自然人とは、直接または間接的に特定することができる者のことです。  
- *処理者*: コントローラーに代わって個人データを処理する自然人または法人、公的機関、団体、その他の組織。  
- *顧客データ*: ビジネス運営における日々の業務で作成および保存されるデータ。

## <a name="microsoft-and-breach-notification"></a>Microsoft と違反の通知

Microsoft では、一般データ保護規則 (GDPR) の下での義務を重く受け止めています。 セキュリティ インシデント/データ侵害とは、Microsoft の機器あるいは Microsoft の施設に保存されている顧客のデータへの違法なアクセス、または顧客データの損失、漏洩、改変を引き起こす可能性のあるものへの不正アクセスなどのイベントを指します。

データ処理者として、Microsoft は、必ずお客様がデータ コントローラーとして GDPR の違反通知要件を満たせるようにしています。 Microsoft からの通知は、その評価に必要な情報を提供しています。 Microsoft は、個人データが判読不能であると確認された場合 (たとえば、キーの整合性が確認された強力に暗号化されたデータ) を除き、お客様に個人データ侵害に関する通知を行います。

データ コントローラーは、データ プライバシーに対するリスクを評価し、お客様の DPA に通知する必要がある侵害かどうかを判断する責任があります。 Microsoft は、GDPR コンプライアンス ポリシーに沿って、その評価を行うために必要な情報を提供します。

最初の通知には、侵害の種類、ユーザーへのおおよその影響、緩和手順 (該当する場合) の説明が記載されています。 最初の通知の時点で Microsoft の調査が完了していない場合は、今後の連絡のための次の手順とスケジュールをお知らせします。 マイクロソフトが個人データの侵害を検出して対応する方法の詳細については、Service Trust Portal の [GDPR の下でのデータ侵害の通知](https://servicetrust.microsoft.com/ViewPage/GDPRBreach)を参照してください。

特定の Microsoft 製品およびサービスに関する侵害の通知の詳細は、以下の通りです。
  
1. **[Office 365](gdpr-breach-Office365.md)**  
    Microsoft は、個人データ漏洩の可能性を低く抑え、侵害が生じた場合は迅速に検出して被害を軽減するために、システム、プロセス、担当者に対する大きな投資を行っています。 詳細については、「[Office 365 におけるデータ セキュリティに対する投資](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-office365#office-365-investments-in-data-security)」を参照してください。

    お客様が侵害に気付いた場合は、Microsoft に問い合わせることができます。 その場合は、Microsoft サポートに連絡してください。Microsoft サポートが、エンジニアリング チームと連携して詳細を確認します。

2. **[Azure および Dynamics 365](gdpr-breach-azure-dynamics.md)**  
    Microsoft には、Microsoft Azure および Dynamics 365 に対する攻撃の影響緩和を目的とした、24 時間 365 日体制のインシデント対応サービスがあります。

    - *侵害の検出*: Microsoft とお客様の両方にセキュリティに関する義務があるため、Azure サービスでは、セキュリティと運用の説明責任を定義した共有責任モデルが導入されています。 Microsoft は、お客様の責任範囲内にあるセキュリティ インシデントの監視、対応は行いません。 適切なサービス契約であれば、お客様のインシデントの場合には、Azure [カスタマー サポート](https://azure.microsoft.com/support/options/)と共同で対応することができます。 また、Microsoft Azure には、お客様がセキュリティ インシデント対応の開発と管理に活用できる、さまざまなサービス ([Azure Security Center](https://azure.microsoft.com/services/security-center/) など) が用意されています。

        Microsoft Azure で侵害の調査をトリガーするイベントの一覧については、「[潜在的なデータ侵害の検出](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#detection-of-potential-breaches)」を参照してください。 「[Azure と GDPR の下での違反の通知](gdpr-breach-azure-dynamics.md)」では、Azure 内で発生するセキュリティ インシデントをどのように Microsoft が調査、管理、対応するかを詳しく述べています。

    - *データ侵害への対応*: Microsoft は、インシデントの機能的影響、回復性、情報の影響を調査し、その侵害の適切な優先度と重大度を判別します。 優先度と重大度は、新しい調査結果と判定に基づき、調査の過程で変わる場合があります。
    法的義務およびお客様へのコミットメントに基づいた調査が確実に行われるように、Microsoft のセキュリティ レスポンス チームが世界各国の法律顧問と緊密に連携します。 これらのプロセスの詳細については、「[Azure のデータ侵害対応](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#azures-data-breach-response)」を参照してください。

    - *お客様への通知*: Microsoft Azure は、必要に応じてデータ侵害をお客様と規制当局に通知します。 次の場合を除き、お客様への通知は、侵害の発生を認識してから 72 時間以内に行われます。

        - Microsoft が、通知を実行すると他のユーザーにとってリスクが増大する判断した場合。
        - 72 時間以内にインシデントの詳細がいくつか分かりそうな場合。 この場合、詳細情報は調査が進むにつれて入手可能。

        詳細については、「[お客様への通知](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#customer-notification)」を参照してください。

3. **[Microsoft サポート/プロフェッショナル サービス](gdpr-breach-Microsoft-Support-Professional-Services.md)**  
    プロフェッショナル サービスの性質上、一部のデータ保護のインシデントはお客様の責任の範囲内に含まれる場合があります。 Microsoft Professional Services によってデータ保護のインシデントと判断された場合は、「[データ保護のインシデント対応プロセスの範囲と制限](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-microsoft-support-professional-services#scope--limits-of-data-protection-incident-response-process)」で説明されている文書化された業界標準対応計画に基づいて、インシデント対応が行われます。

## <a name="learn-more"></a>詳細情報

- [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
