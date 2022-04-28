---
title: 未成年者とストアからのアドインの取得
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 未成年者の個人データを管理する一般データ保護規則 (GDPR) 規制について説明します。
ms.openlocfilehash: 9b348ce47b5deef8f012428a402a4a83eaa6dcf1
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65094242"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>未成年者とストアからのアドインの取得

一般データ保護規則 (GDPR) は、2018 年 5 月 25 日に発効する欧州連合規則です。 これにより、ユーザーは自分のデータに対する権限と保護を行えます。 GDPR の側面の 1 つは、未成年者が親または保護者が承認していない当事者に個人データを送信できないことです。 未成年者として定義されている特定の年齢は、個人が配置されているリージョンによって異なります。

保護者の同意に関する法的規制がある地域には、米国、韓国、英国、欧州連合が含まれます。 これらのリージョンの場合、マイナーは (Azure Active Directory経由で) ストアから新しいOffice アドインを取得し、以前に取得したアドインを実行できないようにブロックされます。 法的規制のない国の場合、ダウンロードの制限はありません。

ユーザーは、Azure Active Directoryで指定されたデータに基づいてマイナーであると判断されます。 組織管理者は、法的年齢グループと、そのユーザーの保護者の同意を宣言する責任があります。

親/保護者が特定のアドインを使用して未成年者に同意した場合、組織管理者は一元的な展開を使用して、同意を得たすべての未成年者にそのアドインを展開できます。

未成年者に対して GDPR に準拠するには、次のいずれかのビルドのOfficeが学校/組織に展開されるようにする必要があります。

 **Word、Excel、PowerPoint、Projectの場合**:

|プラットフォーム|ビルド番号|
|---|---|
|Microsoft 365 Apps for enterprise (現在のチャネル)|9001.2138|
|Microsoft 365 Apps for enterprise (半期Enterprise チャネル)|8431.2159|
|Office 2016 for Windows|16.0.4672.1000|
|Office 2013 for Windows|15.0.5023.1000|
|Office 2016 for Mac|16.11.18020200|
|Web 用 Office|該当なし|

 **Outlookの場合**:

|プラットフォーム|ビルド番号|
|---|---|
|Windows (MSI) のOutlook 2016|ビルドに TBD なし|
|Windows (C2R) のOutlook 2016|16.0.9323.1000|
|Office 2016 for Mac|16.0.9318.1000|
|iOS 用モバイルのOutlook|2.75.0|
|Android 用モバイルOutlook|2.2.145|
|Outlook.com|該当なし|

 **Office 2013 要件**

Windows の Word、Excel、PowerPoint 2013 では、Active Directory 認証ライブラリ (ADAL) が有効になっている場合、同じマイナー チェックがサポートされます。 次に説明するように、コンプライアンスには 2 つのオプションがあります。

- **ADAL を有効にします**。 この記事では、Office 2013 の ADAL を有効にする方法について説明します。[Office クライアントで最新の認証Microsoft 365使用](../../enterprise/modern-auth-for-office-2013-and-2016.md)します。<br/>また、Windows [デバイスで Office 2013 の先進認証を有効にする](../security-and-compliance/enable-modern-authentication.md)に関する記事で説明されているように、ADAL を有効にするためにレジストリ キーを設定する必要もあります。<br/>さらに、Office 2013 の次の 4 月の更新プログラムをインストールする必要があります。

  - [Office 2013 のセキュリティ更新プログラムの説明: 2018 年 4 月 10 日](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)

  - [2018 年 4 月 3 日、Office 2013 (KB4018333) の更新プログラム](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)

- **ADAL を有効にしないでください**。 Office 2013 で ADAL を有効にできない場合は、グループ ポリシーを使用してOffice クライアントのストアを無効にすることが推奨されます。 Office設定でアプリをオフにする方法については、[こちらを参照してください](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))。

## <a name="related-articles"></a>関連記事

[管理センターでアドインを展開する](./manage-deployment-of-add-ins.md)

[管理センターでアドインを管理する](./manage-addins-in-the-admin-center.md)
