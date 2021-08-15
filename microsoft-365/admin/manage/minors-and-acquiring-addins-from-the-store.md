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
ms.openlocfilehash: 7ec9e54865ce21a55dc2bd5bf777e293f105c51e99625bf95ebc1a6dabb7ee22
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53824985"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>未成年者とストアからアドインを取得する

一般データ保護規則 (GDPR) は、2018 年 5 月 25 日に発効する欧州連合の規則です。 これにより、ユーザーはデータに対する権限と保護をユーザーに与えます。 GDPR の側面の 1 つは、未成年者が自分の個人データを親または保護者が承認しない当事者に送信できないことです。 未成年者として定義される特定の年齢は、個人が位置する地域によって異なります。
  
親の同意に関する法的規制を持つ地域には、米国、韓国、英国、および欧州連合が含まれます。 これらの地域では、マイナーが (Azure Active Directory 経由で) Store から新しい Office アドインを取得し、以前に取得したアドインを実行してブロックされます。 法的規制のない国では、ダウンロードの制限はありません。
  
ユーザーは、ユーザーに指定されたデータに基づいてマイナーと判断Azure Active Directory。 組織管理者は、法的年齢グループと、そのユーザーの親の同意を宣言する責任があります。
  
親/保護者が特定のアドインを使用して未成年者に同意した場合、組織管理者は集中展開を使用して、同意を得たすべての未成年者にアドインを展開できます。
  
未成年者に対して GDPR に準拠するには、次のいずれかのビルドの Officeが学校/組織に展開されている必要があります。
 
 **Word の場合Excel、PowerPoint、およびProject:** 

|**プラットフォーム** <br/> |**ビルド番号** <br/> |
|:-----|:-----|
|Microsoft 365 Apps for enterprise (現在のチャネル)  <br/> |9001.2138   <br/> |
|Microsoft 365 Apps for enterprise (半期チャネルEnterprise)  <br/> |8431.2159  <br/> |
|Office 2016 for Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 for Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|Web 用 Office  <br/> |該当なし  <br/> |
   
 **次のOutlook:** 
  
|**プラットフォーム** <br/> |**ビルド番号** <br/> |
|:-----|:-----|
|Outlook 2016のWindows (MSI)  <br/> |ビルド TBD なし  <br/> |
|Outlook 2016のWindows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook iOS 用モバイル  <br/> |2.75.0  <br/> |
|Outlook Android 用モバイル  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |該当なし  <br/> |

 **Office 2013 の要件**
  
Word、Excel、PowerPoint 2013 for Windows では、Active Directory 認証ライブラリ (ADAL) が有効になっている場合と同じマイナー チェックがサポートされます。 次に説明したように、コンプライアンスには 2 つのオプションがあります。
  
- **ADAL を有効にする**。 この記事では、2013 年 2013 年に ADAL を有効にするOfficeクライアントでの最新Microsoft 365の使用Office[説明します](../../enterprise/modern-auth-for-office-2013-and-2016.md)。<br/>また[、「Office 2013 年 2013](../security-and-compliance/enable-modern-authentication.md)年の最新認証を有効にする」の説明に基Windowsする必要があります。<br/>さらに、2013 年 4 月の次の更新プログラムをインストールOfficeがあります。
    
  - [2013 年 4 月 10 日Officeセキュリティ更新プログラムの説明](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [2018 年 4 月 3 日、2013 Office更新プログラム (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **ADAL を有効にしない**。 Office 2013 で ADAL を有効にできない場合は、グループ ポリシーを使用して、Office クライアントのストアを無効にしてください。 アプリの設定をオフにする方法については、Officeを参照[してください](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))。

## <a name="related-articles"></a>関連記事

[管理センターでアドインを展開する](./manage-deployment-of-add-ins.md)

[管理センターでアドインを管理する](./manage-addins-in-the-admin-center.md)
