---
title: 未成年者とストアからのアドインの取得
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 未成年者の個人データを管理する一般的なデータ保護規則 (GDPR) の規則について説明します。
ms.openlocfilehash: dcf2c98906830e0007747e2dd90e67b9dc85a5bb
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103102"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>未成年者とストアからのアドインの取得

一般的なデータ保護規則 (GDPR) は、2018年5月25日に有効になる欧州連合規制です。 ユーザーがデータを保護するための権限が付与されます。 GDPR の1つの側面は、親またはガーディアンが許可されていない個人データを、未成年者が他者に送信することができないことです。 マイナーとして定義された特定の年齢は、個人が配置されている地域によって異なります。
  
保護者の同意に関する法的な規制がある地域には、米国、南韓国、英国、および欧州連合があります。 これらの地域では、マイナーがブロックされます (Azure Active Directory によって)。新しい Office アドインをストアから取得し、以前に取得したアドインを実行します。 法律上の規定がない国では、ダウンロードの制限はありません。
  
ユーザーは、Azure Active Directory で指定されているデータに基づいて、マイナーであると判断されます。 組織管理者は、法務年齢グループと、そのユーザーの上位下位の同意を宣言します。
  
親/ガーディアンが特定のアドインを使用して小規模に同意場合、組織管理者は一元展開を使用して、同意を得ているすべての未成年者にそのアドインを展開できます。
  
GDPR を未成年者に準拠させるには、次のいずれかの Office ビルドが学校/組織に展開されていることを確認する必要があります。
 
 **Word、Excel、PowerPoint、Project の場合**: 

|**プラットフォーム** <br/> |**ビルド番号** <br/> |
|:-----|:-----|
|Microsoft 365 enterprise 用アプリ (現在のチャネル)  <br/> |9001.2138   <br/> |
|Microsoft 365 enterprise 用アプリ (半期エンタープライズチャネル)  <br/> |8431.2159  <br/> |
|Office 2016 for Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 for Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|Web 用 Office  <br/> |N/A  <br/> |
   
 **Outlook の場合**: 
  
|**プラットフォーム** <br/> |**ビルド番号** <br/> |
|:-----|:-----|
|Outlook 2016 for Windows (MSI)  <br/> |ビルドの未定  <br/> |
|Windows 版 Outlook 2016 (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|IOS 用の Outlook mobile  <br/> |2.75.0  <br/> |
|Outlook mobile for Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N/A  <br/> |

 **Office 2013 の要件**
  
Windows 版 Word、Excel、PowerPoint 2013 は、Active Directory 認証ライブラリ (ADAL) が有効になっている場合と同じ未成年者チェックをサポートします。 次に説明するように、2つのコンプライアンスオプションがあります。
  
- **ADAL を有効に**します。 この記事では、office[クライアントでの Microsoft 365 モダン認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)2013 の使用方法について説明します。<br/>「 [Windows デバイスで Office 2013 の先進認証を有効](../security-and-compliance/enable-modern-authentication.md)にする」で説明されているように、レジストリキーを設定して ADAL を有効にする必要もあります。<br/>さらに、Office 2013 用の次の4月の更新プログラムをインストールする必要があります。
    
  - [Office 2013 のセキュリティ更新プログラムの説明: 2018 年4月10日](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [2018年4月3日 Office 2013 の更新プログラム (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **ADAL を有効にしない**でください。 Office 2013 で ADAL を有効にできない場合は、グループポリシーを使用して Office クライアントのストアをオフにすることをお勧めします。 Office 用アプリの設定を無効にする方法については、[ここ](https://technet.microsoft.com/library/cc178992.aspx)を参照してください。

## <a name="related-articles"></a>関連記事

[管理センターでアドインを展開する](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[管理センターでアドインを管理する](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
