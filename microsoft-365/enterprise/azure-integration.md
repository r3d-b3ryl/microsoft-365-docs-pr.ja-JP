---
title: Azure と Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: パスワードMicrosoft 365オンプレミス環境ADシングル サインオンを行う場合は、Azure Microsoft 365と統合します。
ms.openlocfilehash: eaf2b42910c2d0b3a7f672262b2397f8010793ba
ms.sourcegitcommit: 9469d16c6bbd29442a6787beaf7d84fb7699c5e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58400321"
---
# <a name="azure-integration-with-microsoft-365"></a>Azure と Microsoft 365

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365は、Azure Active Directory (Azure AD) を使用して、ユーザー ID を管理します。 Microsoft 365 サブスクリプションには無料の Azure AD サブスクリプションが含まれるので、オンプレミスの Active Directory ドメイン サービス (AD DS) を統合してユーザー アカウントとパスワードを同期したり、シングル サインオンを設定したりできます。 また、高度な機能を購入して、アカウントの管理を向上することもできます。
  
Azure ADは、統合アプリの管理など、他の機能も提供します。この機能を使用すると、アプリのサブスクリプションを拡張Microsoft 365できます。
  
Azure AD 展開アドバイザーを使用して、Microsoft 365 管理センター のガイド付きセットアップと構成エクスペリエンスをMicrosoft 365。

 - [Azure AD Connect アドバイザー](https://aka.ms/aadconnectpwsync)
 - [AD FS 展開アドバイザー](https://aka.ms/adfsguidance)
 - [Azure ADセットアップ ガイド](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure ADエディションとMicrosoft 365 ID 管理

有料サブスクリプションを利用している場合Microsoft 365、無料の Azure サブスクリプションADがあります。 Azure ADを使用して、ユーザー アカウントとグループ アカウントを作成および管理できます。 このサブスクリプションをアクティブ化するには、1 回の登録を完了する必要があります。 その後、Azure ADにアクセスMicrosoft 365 管理センター。 

無料の Azure AD サブスクリプションを登録する手順については、「無料の Azure ADサブスクリプション [を使用する」を参照してください](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)。 azure.microsoft.com に直接アクセスしてサインアップしたり、Microsoft 365 で無料の Azure AD サブスクリプションとは別の Microsoft Azure の試用版または有料サブスクリプションが終了したりします。 
  
無料サブスクリプションを使用すると、オンプレミスのディレクトリと同期し、シングル サインオンを設定し、Salesforce、DropBox などのサービス アプリケーションとして多くのソフトウェアと同期できます。
  
DS 機能、双方向AD、その他の管理機能を強化する場合は、無料サブスクリプションを有料のプレミアム サブスクリプションにアップグレードできます。 詳細については[、「Azure Active Directory」を参照してください](https://azure.microsoft.com/pricing/details/active-directory/)。
  
ユーザー ID モデルと Azure Microsoft 365のAD詳細については、「Microsoft 365 ID モデル」[を参照してください](about-microsoft-365-identity.md)。
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>テナントの機能を拡張Microsoft 365する

|**機能**|**説明**|
|:-----|:-----|
|統合アプリ  <br/> |メール、予定表、連絡先、ユーザー、グループ、ファイル、フォルダーなど、Microsoft 365データへのアクセスを個々のアプリに付与できます。 また、これらのアプリをグローバル管理者レベルで承認し、Azure AD にアプリを登録することで、会社全体で利用AD。 詳細については、「統合アプリ[と Azure AD管理者Microsoft 365を参照してください](integrated-apps-and-azure-ads.md)。  <br/> 「シングル [サインオン」も参照してください](/azure/active-directory/manage-apps/what-is-single-sign-on)。  <br/> |
|Power アプリ  <br/> | Power Appsリストや他のデータ アプリなど、既存のデータ ソースに接続できるモバイル デバイス向SharePointアプリです。 詳細[については、「Create a Power App for a list in SharePoint」](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab)および「Power Apps[ページ」](https://powerapps.microsoft.com/)を参照してください。  <br/> |
   
## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)
