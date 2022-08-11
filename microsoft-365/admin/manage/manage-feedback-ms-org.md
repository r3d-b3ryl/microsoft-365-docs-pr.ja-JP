---
title: 組織に対する Microsoft フィードバックを管理する
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 製品に関してユーザーが Microsoft に送信できるフィードバックを管理します。
ms.openlocfilehash: d32b9f1150443bc4fc4e859004949d6f27b6914d
ms.sourcegitcommit: 6bff75867764335685f972943170c7db46e33a6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "67300806"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>組織に対する Microsoft フィードバックを管理する

Microsoft 365 組織の管理者として、Microsoft 365 アプリケーションを使用する場合に、フィードバックの収集とユーザーのカスタマー エンゲージメント エクスペリエンスを管理するのに役立ついくつかのポリシーが追加されました。 これらのポリシーごとに、組織内の既存の Azure Active Directory グループを作成して使用できます。 これらのポリシーを使用すると、組織内のさまざまな部署が Microsoft にフィードバックを送信する方法を制御できます。 Microsoft は、お客様から送信されたすべてのフィードバックを確認し、このフィードバックを使用して製品を改善します。 フィードバック エクスペリエンスを **オン** にしておくと、ユーザーが使用している Microsoft 製品についてユーザーが何を言っているかを確認できます。 ユーザーから収集したフィードバックは、まもなく<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で利用できるようになります。

フィードバックの種類と Microsoft によるユーザー フィードバックの使用方法の詳細については、「 [組織の Microsoft フィードバックについて学習する](../misc/feedback-user-control.md)」を参照してください。

次の表は、次のフィードバック ポリシーの表に示すフィードバック ポリシーに現在接続されているアプリとサービスを表しています。 スクリーンショットの例については、次の表を参照してください。

|**Apps & Services**|**製品内フィードバック** <br> |**製品内アンケート** <br> |**メタデータ コレクション** <br> |**顧客エンゲージメント** <br> |
|:-----|:-----|:-----|:-----|:-----|
|**Access**|はい|はい|はい|はい|
|**Excel**|はい|はい|はい|はい|
|**Office.com**|近日公開|近日公開|近日公開|近日公開|
|**OneNote**|はい|はい|はい|はい|
|**OneDrive**|[現在、他のコントロールによって管理されている一部の設定。](/onedrive/disable-contact-support-send-feedback)||||
|**Outlook**|近日公開|近日公開|近日公開|近日公開|
|**PowerPoint**|はい|はい|はい|はい|
|**プロジェクト**|近日公開|近日公開|近日公開|近日公開|
|**発行元**|はい|はい|はい|はい|
|**SharePoint**|[現在、他のコントロールによって管理されている一部の設定。](/powershell/module/sharepoint-online/set-spotenant)||||
|**Teams**|[現在、他のコントロールによって管理されている一部の設定。](/microsoftteams/manage-feedback-policies-in-teams)||||
|**Word**|はい|はい|はい|はい|
|**Visio**|はい|はい|はい|はい|
|**Yammer**|はい|はい|はい|はい|

[製品内のアンケートとフィードバックの例については、こちらを参照してください。](/microsoft-365/admin/misc/feedback-user-control#in-product-surveys)

**メタデータ コレクション**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="スクリーンショット: メタデータの例を示すフィードバック ページ":::

**顧客エンゲージメント**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="スクリーンショット: 製品内の顧客調査の質問の例":::

## <a name="before-you-begin"></a>はじめに

これらのポリシーを使用するには、デバイスが最小ビルド番号である必要があります。 詳細については、次の表を参照してください。

|**ビルド#**|**Win32**|**iOS**|**Android**|**Mac**|**Web**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|製品内フィードバック|少なくともバージョン 2010|少なくとも 2.42|少なくとも 16.0.13328|少なくとも 16.42|公開|
|製品内アンケート|少なくともバージョン 2010|少なくとも 2.42|16.0.13426 以上|少なくとも 16.42|ロールアウトの保留中|
|メタデータ コレクション|少なくともバージョン 2010|少なくとも 2.42|少なくとも 16.0.13328|少なくとも 16.42|公開|
|顧客エンゲージメント|少なくともバージョン 2010|少なくとも 2.42|16.0.13426 以上|少なくとも 16.42|ロールアウトの保留中|

## <a name="specific-policies-you-can-configure"></a>構成できる特定のポリシー

### <a name="feedback-policies"></a>フィードバック ポリシー

|**[ポリシー名]**|**既定の状態**|**コントロールの概要**|
|:-----|:-----|:-----|
|ユーザーにフィードバック ポータルへのアクセスを許可する|オン|フィードバック ポータルへのユーザー アクセスを管理する|
|ユーザーが Microsoft にフィードバックを送信できるようにする|オン|アプリケーション間のフィードバック エントリ ポイントを制御する|
|ユーザーが Microsoft からの製品内アンケートを受信して回答できるようにする|オン|製品内のアンケート プロンプトを制御する|
|ユーザーが Microsoft にフィードバックを送信するときに、スクリーンショットや添付ファイルを含めることを許可する|オフ|ユーザーがフィードバック/アンケートで送信することを決定できるメタデータを決定します|
|ユーザーが提出したフィードバックを Microsoft がフォローアップできるようにする|Off|ユーザーがフィードバック/アンケートで連絡先情報を共有できるかどうかを決定します|
|フィードバックが Microsoft に送信されるときに、ログ ファイルやコンテンツ サンプルを含めることを許可する|Off|ユーザーがフィードバック/アンケートで送信することを決定できるメタデータを決定します|

> [!NOTE]
> **[ユーザーにフィードバック ポータルへのアクセスを許可する**] ポリシーはクラウド ポリシーです。 このポリシーは ADMX で定義されておらず、対応するレジストリ キーを使用してポリシーを設定することはできません。 クラウド ポリシーを作成して適用する必要があります。 これは、フィードバック ポータルがクラウド ポリシー サービスを呼び出す Web アプリケーションであるため、これはクラウド ポリシーです。これは Web アプリケーションでもあり、サインインするユーザーのポリシーを要求します。 このポリシーが構成されている場合、フィードバック ポータルは、クラウド ポリシー サービスからの応答で構成されたポリシー値を受け取ります。

## <a name="configure-policies"></a>ポリシーを構成する

これらのポリシー設定を構成するには、Office クラウド ポリシー サービスを使用します。 詳細については、「 [Office クラウド ポリシー サービスの概要](/deployoffice/overview-office-cloud-policy-service)」を参照してください。 Office クラウド ポリシー サービス UI 内で "フィードバック" または "アンケート" を検索して、それらを構成するポリシー設定を見つけることができます。 

これらのポリシー設定は、グループ ポリシーを使用する場合にも使用できます。 これらのポリシー設定を使用するには、2021 年 3 月 22 日にリリースされた [管理用テンプレート ファイル (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) の少なくともバージョン 5146.1000 をダウンロードします。

これらのポリシー設定は、ユーザー構成\ポリシー\管理用テンプレート\Microsoft Office 2016\Privacy\Trust Center にあります。

> [!NOTE]
> クライアント アプリケーションの更新には数時間かかります。
