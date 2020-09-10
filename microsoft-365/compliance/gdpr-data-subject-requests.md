---
title: GDPR および CCPA のためのデータ対象要求
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR、CCPA
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
description: Microsoft の製品とサービスを使用して、一般データ保護規則 (GPDR) およびカリフォルニア州消費者プライバシー法 (CCPA) に従って DSR を完了する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a9dc9c390aa912bbbfa433a6c98acc188eb0f024
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417960"
---
# <a name="data-subject-requests-and-the-gdpr-and-ccpa"></a>データ対象要求と GDPR および CCPA

一般データ保護規則 (GDPR) では、欧州連合 (EU) 内の人々に商品やサービスを提供する、または EU 居住者向けのデータの収集と分析を実行する会社に対して、新しい規則を導入します。GDPR は、個人やその企業がどの場所にあるかに関係なく適用されます。 詳細については、「[GDPR 概要トピック](gdpr.md)」を参照してください。

同様に、カリフォルニア州消費者プライバシー法 (CCPA) では、個人情報の削除、アクセスおよび受信 (移植性) など、GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。  また、CCPA では、特定の開示、権利の行使を選択する際の差別に対する保護、"売上" として分類された特定のデータ転送の "オプトアウト/オプトイン" 要件を規定します。 このドキュメントは、Microsoft の製品とサービスの使用における、GDPR および CCPA に基づくデータ主体の要求 (DSR) の完了に関する情報を提供します。

- [Office 365](gdpr-dsr-Office365.md)
- [Azure](gdpr-dsr-Azure.md)
- [Intune](gdpr-dsr-Intune.md)
- [Dynamics 365](gdpr-dsr-Dynamics365.md)
- [Visual Studio ファミリ](gdpr-dsr-visual-studio-family.md)
- [Azure DevOps Services](gdpr-dsr-vsts.md)
- [Microsoft サポート/プロフェッショナル サービス](gdpr-dsr-prof-services.md)

## <a name="terminology"></a>用語

このドキュメントで使用されている GDPR 用語の役に立つ定義:

- *データ コントローラー (コントローラー)*: 法人、公的機関、団体、その他の組織。単独または他者と協力して、個人データの処理の目的と方法を決定します。  
- *個人データ*と*データ主体*: 特定されたまたは特定可能な自然人 (データ主体) に関連するあらゆる情報。特定可能な自然人とは、直接または間接的に特定することができる者のことです。  
- *処理者*: コントローラーに代わって個人データを処理する自然人または法人、公的機関、団体、その他の組織。  
- *顧客データ*: ビジネス運営における日々の業務で作成および保存されるデータ。

## <a name="what-is-a-dsr"></a>DSR とは?

一般データ保護規則 (GDPR) は、規制においてデータ主体と呼ばれる人に、雇用主または他の種類の機関や組織 (データ コントローラーまたは単にコントローラーと呼ばれます) によって収集された個人データを管理する権限を与えます。 GDPR では、個人データに対するデータ主体固有の権限が付与されます。このような権限には、個人データのコピーの取得、個人データの変更の要求、個人データの処理の制限、個人データの削除、または別のコントローラーに移動できる電子的な形式での個人データの受け取りが含まれます。

カリフォルニア州消費者プライバシー法 (CCPA) では、個人情報の削除、アクセスおよび受信 (移植性) など、GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。  

管理者は、要求されたアクションを実行するか、または管理者が DSR に対応できない理由についての説明を提供することで、各 DSR を速やかに検討し、実質的な対応を提供する必要があります。 コントローラーは、特定の DSR の適切な処理について自身の法律またはコンプライアンスのアドバイザーに相談する必要があります。

DSR の完了には、組織の GDPR コンプライアンス規則に従って、いくつかのプロセスが必要になる場合があります。
  
- **検出**。 DSR を完了するために必要なデータを特定するプロセス。
- **アクセス**。 検出された情報の取得とデータ主体への潜在的な伝送。
- **修正**。 変更またはその他の要求された個人データの変更を実施します。
- **制限**。 アクセスを制限する、または Microsoft クラウドからデータを削除することにより、個人データのアクセスまたは処理を変更します。
- **エクスポート**。 GDPR の「データの移植の権利」で規定されているように、「構造化された一般的に使用されているコンピューターが読み取り可能な形式」の個人データをデータ主体に提供します。
- **Delete** Microsoft クラウドから個人データを完全に削除します。

## <a name="specific-dsr-considerations"></a>特定の DSR に関する考慮事項

### <a name="insights-generated-by-microsoft-products-or-services"></a>Microsoft の製品またはサービスにより生成された分析情報

[分析情報](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)はサービス (MyAnalytics など) によって生成される場合があります。Office 365 には、分析情報を使用するユーザーと組織にこの情報を提供するオンライン サービスが含まれています。 これらのサービスによって生成されたデータによって、DSR に関連する個人データが生成される場合あります。 サービス固有の DSR プロセスに関する詳細については、以下のリストにあるリンクを参照してください。  

### <a name="dsrs-for-system-generated-logs"></a>システム生成ログに関する DSR

Microsoft によって生成されたログと関連データには、"個人データ" の GDPR 定義に基づき個人に関するものとしてみなされるデータが含まれる場合があります。 システム生成ログのデータの制限または修正はサポートされていません。 システム生成ログのデータは、Microsoft のクラウド内で実行された実際のアクションや診断データを構成しているため、変更すると、アクションの履歴記録が損なわれ、詐欺やセキュリティのリスクが増大します。 Microsoft は、DSR の完了に必要となる可能性があるシステム生成ログに対するアクセス、エクスポート、削除の各機能を提供します。 該当するデータには次のようなものがあります。  

- 製品およびサービスの利用状況データ (ユーザー アクティビティ ログなど)
- ユーザー検索要求およびクエリ データ
- ユーザーまたはその他のシステムによるシステム機能および相互作用の結果として、製品およびサービスによって生成されたデータ。  

### <a name="yammer-and-kaizala"></a>Yammer と Kaizala

ユーザーのアカウントを削除しても、システムで生成された Yammer および Kaizala のログは削除されません。 これらのアプリケーションからデータを削除するには、次のいずれかのリソースを参照してください。

- [Yammer Enterprise で GDPR データ主体の要求を管理する](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [Kaizala でユーザーの組織データをエクスポートまたは削除する](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a>国内クラウド

一部の国内クラウドでは、グローバル IT 管理者がシステム生成ログを削除する必要があります。

### <a name="microsoft-services"></a>Microsoft サービス

お客様の組織またはユーザーが Microsoft の製品とサービスに関連するサポートを受けるために Microsoft と連携している場合、このデータの一部に個人データが含まれる可能性があります。 詳細については、「[GDPR のための Microsoft サポート/プロフェッショナル サービス データ主体の要求](gdpr-dsr-prof-services.md)」を参照してください。

### <a name="microsoft-controller-products"></a>Microsoft コントローラー製品

状況によっては、組織のユーザーは Microsoft がデータ コントローラーである Microsoft の製品またはサービスにアクセスすることもあります。 このような場合、ユーザーは自分自身の DSR を Microsoft に対して直接開始する必要があります。また、Microsoft はユーザーに対する要求を直接満たします。

### <a name="third-party-products"></a>サード パーティ製品

Microsoft アカウント認証を介してアクセスしたサード パーティの製品とサービスの場合、すべてのデータ主体の要求は該当するサード パーティに送信される必要があります。

## <a name="data-subject-request-admin-tools"></a>データ主体の要求の管理ツール

- **セキュリティ/コンプライアンス センター**: ユーザーが生成したデータは、[セキュリティ/コンプライアンス センター](https://aka.ms/stpsecurityandcompliance)を使用するか、アプリケーション内の機能を使用してエクスポートします。
- **Azure AD 管理センター**: Azure Active Directory および関連サービスからのデータ主体の削除には、[Azure AD 管理センター](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/UserManagementMenuBlade/Allusers/menuId/)を使用します。
- **Microsoft データ ログのエクスポート**: システム生成のログは、テナント管理者が [Microsoft データ ログのエクスポート](https://aka.ms/MicrosoftGDPR)を使用することでエクスポートできます。

## <a name="learn-more"></a>詳細情報

- [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
