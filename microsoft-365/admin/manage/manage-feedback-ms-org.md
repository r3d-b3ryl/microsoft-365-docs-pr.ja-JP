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
localization_priority: Normal
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
description: ユーザーが Microsoft 製品に関して Microsoft に送信できるフィードバックを管理します。
ms.openlocfilehash: 7d6d607182a546e869a9f92e84adfa31f7e02a26
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59179023"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>組織に対する Microsoft フィードバックを管理する

Microsoft 365 組織の管理者として、Microsoft 365 アプリケーションを使用する際にユーザーのフィードバック コレクションとカスタマー エンゲージメント エクスペリエンスを管理するのに役立ついくつかのポリシーが追加されました。 これらのポリシーごとに、組織内の既存の Azure Active directory グループを作成して使用できます。 これらの警察では、組織内の異なる部署が Microsoft にフィードバックを送信する方法を制御できます。 Microsoft は、お客様から送信されたフィードバックを確認し、このフィードバックを使用して製品を改善します。 フィードバック エクスペリエンスを **オンに保** つことで、ユーザーが使用している Microsoft 製品についてユーザーが何を言っているのかを確認できます。 ユーザーから収集したフィードバックは、すぐにこの<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">サイトで</a>Microsoft 365 管理センター。

フィードバックの種類と Microsoft がユーザー フィードバックを使用する方法の詳細については、「組織の Microsoft フィードバックについて [」を参照してください](../misc/feedback-user-control.md)。

次の表は、以下のフィードバック ポリシーの表に示すフィードバック ポリシーに現在接続されているアプリとサービスを表しています。 スクリーンショットの例については、以下の表を参照してください。

|**アプリ & サービス**|**製品内フィードバック** <br> |**製品内アンケート** <br> |**メタデータ コレクション** <br> |**顧客エンゲージメント** <br> |
|:-----|:-----|:-----|:-----|:-----|
|**Access**|はい|はい|はい|はい|
|**Excel**|はい|はい|はい|はい|
|**Office.com**|近日公開|近日公開|近日公開|近日公開|
|**OneNote**|はい|はい|はい|はい|
|**OneDrive**|[他のコントロールによって現在管理されている設定の一部。](/onedrive/disable-contact-support-send-feedback)||||
|**Outlook**|近日公開|近日公開|近日公開|近日公開|
|**PowerPoint**|はい|はい|はい|はい|
|**Project**|近日公開|近日公開|近日公開|近日公開|
|**発行元**|はい|はい|はい|はい|
|**SharePoint**|[他のコントロールによって現在管理されている設定の一部。](/powershell/module/sharepoint-online/set-spotenant)||||
|**Teams**|[他のコントロールによって現在管理されている設定の一部。](/microsoftteams/manage-feedback-policies-in-teams)||||
|**Word**|はい|はい|はい|はい|
|**Visio**|はい|はい|はい|はい|
|**Yammer**|はい|はい|はい|はい|

[製品内のアンケートとフィードバックの例については、こちらを参照してください。](/microsoft-365/admin/misc/feedback-user-control#in-product-surveys)

**メタデータ コレクション**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="スクリーンショット: メタデータの例を示すフィードバック ページ":::

**顧客エンゲージメント**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="スクリーンショット: 製品内のお客様調査の質問例":::

## <a name="before-you-begin"></a>開始する前に

これらのポリシーを使用するには、デバイスが最小ビルド番号に設定されている必要があります。 詳細については、次の表を参照してください。

|**ビルド#**|**Win32**|**iOS**|**Android**|**Mac**|**Web**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|製品内フィードバック|少なくとも 16.0.13328|少なくとも 2.42|少なくとも 16.0.13328|少なくとも 16.42|一般公開|
|製品内アンケート|少なくとも 16.0.13328|少なくとも 2.42|少なくとも 16.0.13426|少なくとも 16.42|保留中のロールアウト|
|メタデータ コレクション|少なくとも 16.0.13328|少なくとも 2.42|少なくとも 16.0.13328|少なくとも 16.42|一般公開|
|顧客エンゲージメント|少なくとも 16.0.13328|少なくとも 2.42|少なくとも 16.0.13426|少なくとも 16.42|保留中のロールアウト|

## <a name="specific-policies-you-can-configure"></a>構成できる特定のポリシー

### <a name="feedback-policies"></a>フィードバック ポリシー

|**[ポリシー名]**|**既定の状態**|**コントロールの概要**|
|:-----|:-----|:-----|
|ユーザーが Microsoft にフィードバックを送信するを許可する|オン|アプリケーション全体のフィードバック エントリ ポイントを制御する|
|ユーザーが Microsoft から製品内アンケートを受け取り、対応できる|オン|製品内のアンケート プロンプトを制御する|
|ユーザーが Microsoft にフィードバックを送信するときにスクリーンショットと添付ファイルを含める|オフ|ユーザーがフィードバック/アンケートで送信を決定できるメタデータを決定します。|
|ユーザーが送信したフィードバックのフォローアップを Microsoft に許可する|オフ|ユーザーがフィードバック/アンケートと連絡先情報を共有できるかどうかを決定します。|
|フィードバックが Microsoft に送信された場合、ユーザーにログ ファイルとコンテンツ サンプルを含め許可する|オフ|ユーザーがフィードバック/アンケートで送信できるメタデータを決定します。|

## <a name="configure-policies"></a>ポリシーの構成

1. に移動 [https://config.office.com](https://config.office.com) してログインします。
1. [カスタマイズ **] を選択** し **、[ポリシーの管理] を選択します**。
1. **[作成]** を選択します。
1. 名前 **と説明を****入力します**。
1. 構成する Azure Active directory グループを選択します。
1. フィードバックと **アンケートを****検索します**。
1. リストされているポリシーごとに、必要な値を設定します。

詳細については、「クラウド ポリシー[サービスの概要」Office参照してください](/deployoffice/overview-office-cloud-policy-service)。

これらのポリシー設定は、グループ ポリシーを使用する場合にも使用できます。 これらのポリシー設定を使用するには、2021 年 3 月 22 日にリリースされた管理用テンプレート ファイル [(ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030)の少なくともバージョン 5146.1000 をダウンロードします。

これらのポリシー設定は、ユーザー構成 -> ポリシー -> 管理用テンプレート -> Microsoft Office 2016 -> プライバシー -> セキュリティ センターにあります。

> [!NOTE]
> クライアント アプリケーションの更新には数時間かかります。
