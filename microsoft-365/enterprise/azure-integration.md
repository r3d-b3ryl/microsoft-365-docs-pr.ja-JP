---
title: Azure と Microsoft 365 の統合
ms.author: josephd
author: JoeDavies-MSFT
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
description: パスワード同期またはシングル サインオンをオンプレミス環境AD場合は、Microsoft 365 と Azure ADを統合します。
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905334"
---
# <a name="azure-integration-with-microsoft-365"></a>Azure と Microsoft 365 の統合

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 では、Azure Active Directory (Azure Active Directory AD) を使用して、ユーザー ID を背後で管理します。 Microsoft 365 サブスクリプションには無料の Azure AD サブスクリプションが含まれています。そのため、オンプレミスの Active Directory ドメイン サービス (AD DS) を統合してユーザー アカウントとパスワードを同期したり、シングル サインオンを設定したりできます。 また、高度な機能を購入して、アカウントの管理を向上することもできます。
  
Azure ADは、Microsoft 365 サブスクリプションの拡張およびカスタマイズに使用できる統合アプリの管理など、他の機能も提供します。
  
Microsoft 365 管理センターでのガイド付きセットアップと構成エクスペリエンスには、Azure AD 展開アドバイザーを使用できます (Microsoft 365 にサインインする必要があります)。

 - [Azure AD Connect アドバイザー](https://aka.ms/aadconnectpwsync)
 - [AD FS 展開アドバイザー](https://aka.ms/adfsguidance)
 - [Azure ADセットアップ ガイド](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure ADエディションと Microsoft 365 ID 管理

Microsoft 365 の有料サブスクリプションをお持ちの場合は、無料の Azure サブスクリプションADがあります。 Azure ADを使用して、ユーザー アカウントとグループ アカウントを作成および管理できます。 このサブスクリプションをアクティブ化するには、1 回の登録を完了する必要があります。 その後、Microsoft 365 管理センターから Azure ADにアクセスできます。 

無料の Azure AD サブスクリプションを登録する手順については、「無料の Azure ADサブスクリプション [を使用する」を参照してください](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)。 azure.microsoft.com に直接アクセスしてサインアップしたり、Microsoft 365 で無料の Azure AD サブスクリプションとは別の試用版または有料サブスクリプションを利用したりします。 
  
無料サブスクリプションを使用すると、オンプレミスのディレクトリと同期し、シングル サインオンを設定し、Salesforce、DropBox などのサービス アプリケーションとして多くのソフトウェアと同期できます。
  
DS 機能、双方向AD、その他の管理機能を強化する場合は、無料サブスクリプションを有料のプレミアム サブスクリプションにアップグレードできます。 詳細については [、「Azure Active Directory エディション」を参照してください](https://azure.microsoft.com/pricing/details/active-directory/)。
  
Microsoft 365 および Azure ADについては [、「Microsoft 365 ID モデル」を参照してください](about-microsoft-365-identity.md)。
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Microsoft 365 テナントの機能を拡張する

|**機能**|**説明**|
|:-----|:-----|
|統合アプリ  <br/> |個々のアプリに、メール、予定表、連絡先、ユーザー、グループ、ファイル、フォルダーなどの Microsoft 365 データへのアクセス権を付与できます。 また、これらのアプリをグローバル管理者レベルで承認し、Azure AD にアプリを登録することで、会社全体で利用AD。 詳細については [、「Integrated Apps and Azure AD Microsoft 365](integrated-apps-and-azure-ads.md)管理者向け」を参照してください。  <br/> 「シングル [サインオン」も参照してください](/azure/active-directory/manage-apps/what-is-single-sign-on)。  <br/> |
|PowerApps  <br/> | Power Apps は、SharePoint リストや他のデータ アプリなどの既存のデータ ソースに接続できるモバイル デバイス向けアプリです。 詳細 [については、「Create a PowerApp for a list in SharePoint Online」](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) および [「PowerApps」ページ](https://powerapps.microsoft.com/) を参照してください。  <br/> |
   
## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)