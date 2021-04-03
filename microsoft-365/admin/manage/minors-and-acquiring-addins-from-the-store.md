---
title: 未成年者とストアからアドインを取得する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: 未成年者の個人データを管理する一般データ保護規則 (GDPR) の規制について学ぶ。
ms.openlocfilehash: e7f53a5a6b64f29f5029f0080fef44439c926edb
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580920"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>未成年者とストアからアドインを取得する

一般データ保護規則 (GDPR) は、2018 年 5 月 25 日に発効する欧州連合の規則です。 これにより、ユーザーはデータに対する権限と保護をユーザーに与えます。 GDPR の側面の 1 つは、未成年者が自分の個人データを親または保護者が承認しない当事者に送信できないことです。 未成年者として定義される特定の年齢は、個人が位置する地域によって異なります。
  
親の同意に関する法的規制を持つ地域には、米国、韓国、英国、および欧州連合が含まれます。 これらの地域では、マイナーが (Azure Active Directory 経由で) ストアから新しい Office アドインを取得し、以前に取得したアドインを実行してブロックされます。 法的規制のない国では、ダウンロードの制限はありません。
  
ユーザーは、Azure Active Directory で指定されたデータに基づいてマイナーと判断されます。 組織管理者は、法的年齢グループと、そのユーザーの親の同意を宣言する責任があります。
  
親/保護者が特定のアドインを使用して未成年者に同意した場合、組織管理者は集中展開を使用して、同意を得たすべての未成年者にアドインを展開できます。
  
未成年者に対して GDPR に準拠するには、次の 1 つのビルドの Officeが学校/組織に展開されている必要があります。
 
 **Word、Excel、PowerPoint、および Project の場合**: 

|**プラットフォーム** <br/> |**ビルド番号** <br/> |
|:-----|:-----|
|Microsoft 365 Apps for enterprise (Current Channel)  <br/> |9001.2138   <br/> |
|Microsoft 365 Apps for enterprise (半期エンタープライズ チャネル)  <br/> |8431.2159  <br/> |
|Office 2016 for Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 for Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|Webアプリ上の Office  <br/> |該当なし  <br/> |
   
 **Outlook の場合**: 
  
|**プラットフォーム** <br/> |**ビルド番号** <br/> |
|:-----|:-----|
|Outlook 2016 for Windows (MSI)  <br/> |ビルド TBD なし  <br/> |
|Outlook 2016 for Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook mobile for iOS  <br/> |2.75.0  <br/> |
|Android 用 Outlook モバイル  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |該当なし  <br/> |

 **Office 2013要件**
  
Word、Excel、PowerPoint 2013 for Windows では、Active Directory 認証ライブラリ (ADAL) が有効になっている場合と同じマイナー チェックがサポートされます。 次に説明したように、コンプライアンスには 2 つのオプションがあります。
  
- **ADAL を有効にする**。 この記事では、ADAL for Office 2013: [Microsoft 365](../../enterprise/modern-auth-for-office-2013-and-2016.md)モダン認証をクライアントとOfficeします。<br/>また、「Windows デバイスで最新の認証を有効にする」の説明に基Office 2013 [する必要があります](../security-and-compliance/enable-modern-authentication.md)。<br/>さらに、次の 4 月の更新プログラムをインストールする必要Office 2013。
    
  - [2018 年 4 月 10 日Office 2013セキュリティ更新プログラムの説明](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [2018 年 4 月 3 日、Office 2013更新プログラム (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **ADAL を有効にしない**。 ADAL を Office 2013 で有効にできない場合は、グループ ポリシーを使用してクライアントのストアを無効にOfficeします。 アプリの設定をオフにする方法については、Officeを参照 [してください](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))。

## <a name="related-articles"></a>関連記事

[管理センターでアドインを展開する](./manage-deployment-of-add-ins.md)

[管理センターでアドインを管理する](./manage-addins-in-the-admin-center.md)
