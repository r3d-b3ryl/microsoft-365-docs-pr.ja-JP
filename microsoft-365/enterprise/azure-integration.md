---
title: Microsoft 365 との Azure の統合
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
description: オンプレミス環境でのパスワード同期またはシングルサインオンを行う場合は、Microsoft 365 を Azure AD と統合します。
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384747"
---
# <a name="azure-integration-with-microsoft-365"></a>Microsoft 365 との Azure の統合

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 では、Azure Active Directory (Azure AD) を使用して、バックグラウンドでユーザー id を管理しています。 Microsoft 365 サブスクリプションには、オンプレミスの Active Directory ドメインサービス (AD DS) を統合してユーザーアカウントとパスワードを同期したり、シングルサインオンを設定したりできるように、Azure AD サブスクリプションが無料で用意されています。 また、高度な機能を購入して、アカウントをより適切に管理することもできます。
  
Azure AD では、統合アプリの管理などのその他の機能も提供されており、これを使用して Microsoft 365 サブスクリプションを拡張およびカスタマイズできます。
  
Microsoft 365 管理センターで、ガイド付きのセットアップと構成の手順に Azure AD 展開アドバイザーを使用できます (Microsoft 365 にサインインする必要があります)。

 - [Azure AD Connect advisor](https://aka.ms/aadconnectpwsync)
 - [AD FS 展開アドバイザー](https://aka.ms/adfsguidance)
 - [Azure AD セットアップガイド](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure AD エディションと Microsoft 365 id 管理

Microsoft 365 への有料サブスクリプションを保有している場合は、Azure AD サブスクリプションも無料で利用できます。 Azure AD を使用して、ユーザーアカウントとグループアカウントを作成および管理できます。 このサブスクリプションをアクティブ化するには、1回限りの登録を完了する必要があります。 その後、Microsoft 365 管理センターから Azure AD にアクセスできます。 

無料の Azure AD サブスクリプションを登録する手順については、「 [Free AZURE ad サブスクリプションを使用](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)する」を参照してください。 Azure.microsoft.com に直接進んでサインアップしないでください。 microsoft Azure の試用版または有償版サブスクリプションが、Microsoft 365 を使用して無料の Azure AD サブスクリプションとは別のものになります。 
  
無料のサブスクリプションを使用すると、オンプレミスのディレクトリと同期したり、シングルサインオンを設定したり、サービスアプリケーション (Salesforce、DropBox など) などの多くのソフトウェアと同期したりすることができます。
  
拡張された AD DS 機能、双方向同期、およびその他の管理機能が必要な場合は、無料のサブスクリプションを有料プレミアムサブスクリプションにアップグレードできます。 詳細については、「 [Azure Active Directory のエディション](https://azure.microsoft.com/pricing/details/active-directory/)」を参照してください。
  
Microsoft 365 と Azure AD の詳細については、「 [microsoft 365 identity モデル](about-microsoft-365-identity.md)」を参照してください。
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Microsoft 365 テナントの機能を拡張する

|**機能**|**説明**|
|:-----|:-----|
|統合アプリ  <br/> |メール、予定表、連絡先、ユーザー、グループ、ファイル、フォルダーなど、Microsoft 365 データへの個別のアプリのアクセスを許可することができます。 また、グローバル管理者レベルでこれらのアプリを承認し、Azure AD にアプリを登録することにより、会社全体でそれらを利用できるようにすることもできます。 Formore の情報については、「 [Microsoft 365 管理者向けの統合アプリおよび AZURE AD](integrated-apps-and-azure-ads.md)」を参照してください。  <br/> また [、「シングルサインオン](https://go.microsoft.com/fwlink/p/?LinkId=698604)」を参照してください。  <br/> |
|PowerApps  <br/> | Power apps は、SharePoint リストやその他のデータアプリなどの既存のデータソースに接続できるモバイルデバイス用のフォーカスアプリです。 詳細については、「 [SharePoint Online のリスト用の PowerApp の作成](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) 」および「 [PowerApps ページ](https://powerapps.microsoft.com/) 」を参照してください。  <br/> |
   
## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)
