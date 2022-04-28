---
title: Azure と Microsoft 365の統合
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
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
description: パスワード同期またはシングル サインオンをオンプレミス環境で行う場合は、Microsoft 365とAzure ADを統合します。
ms.openlocfilehash: bebbad10d0fb7a61437dcb24398ebb88d90db739
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096834"
---
# <a name="azure-integration-with-microsoft-365"></a>Azure と Microsoft 365の統合

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365では、Azure Active Directory (Azure AD) を使用して、バックグラウンドでユーザー ID を管理します。 Microsoft 365 サブスクリプションには、オンプレミスの Active Directory Domain Services (AD DS) を統合してユーザー アカウントとパスワードを同期したり、シングル サインオンを設定したりできるように、無料のAzure AD サブスクリプションが含まれています。 高度な機能を購入して、アカウントをより適切に管理することもできます。
  
Azure ADには、統合アプリの管理など、Microsoft 365 サブスクリプションの拡張とカスタマイズに使用できるその他の機能も用意されています。
  
Microsoft 365 管理センターのガイド付きセットアップと構成エクスペリエンスには、Azure ADデプロイ アドバイザーを使用できます (Microsoft 365にサインインする必要があります)。

 - [Azure AD Connect advisor](https://aka.ms/aadconnectpwsync)
 - [AD FS 展開アドバイザー](https://aka.ms/adfsguidance)
 - [Azure ADセットアップ ガイド](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure AD エディションとMicrosoft 365 ID 管理

Microsoft 365の有料サブスクリプションをお持ちであれば、無料のAzure AD サブスクリプションもあります。 Azure ADを使用して、ユーザー アカウントとグループ アカウントを作成および管理できます。 このサブスクリプションをアクティブ化するには、1 回限りの登録を完了する必要があります。 その後、Microsoft 365 管理センターからAzure ADにアクセスできます。 

無料のAzure AD サブスクリプションを登録する手順については、「[無料のAzure AD サブスクリプションを使用する](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)」を参照してください。 azure.microsoft.com に直接アクセスしてサインアップしたり、Microsoft 365を使用して無料のAzure AD サブスクリプションとは別のMicrosoft Azureに試用版または有料サブスクリプションが作成されたりします。 
  
無料サブスクリプションを使用すると、オンプレミス ディレクトリと同期したり、シングル サインオンを設定したり、Salesforce、DropBox などの多くのソフトウェアをサービス アプリケーションとして同期したりできます。
  
強化された AD DS 機能、双方向同期、およびその他の管理機能が必要な場合は、無料サブスクリプションを有料の Premium サブスクリプションにアップグレードできます。 詳細については、「[Azure Active Directory エディション](https://azure.microsoft.com/pricing/details/active-directory/)」を参照してください。
  
Microsoft 365とAzure ADの詳細については、「[Microsoft 365 ID モデル」を](deploy-identity-solution-identity-model.md)参照してください。
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Microsoft 365 テナントの機能を拡張する

|**機能**|**説明**|
|:-----|:-----|
|統合アプリ  <br/> |メール、予定表、連絡先、ユーザー、グループ、ファイル、フォルダーなど、Microsoft 365 データへのアクセス権を個々のアプリに付与できます。 また、AZURE AD **DC 管理者** または **グローバル管理者** レベルでこれらのアプリを承認し、Azure ADにアプリを登録して会社全体で利用できるようにすることもできます。 詳細については、「[Microsoft 365管理者向けの統合アプリとAzure AD](integrated-apps-and-azure-ads.md)」を参照してください。<br/> 詳細については、「[管理者の役割について](/microsoft-365/admin/add-users/about-admin-roles?)」を参照してください。 <br/> [シングル サインオン](/azure/active-directory/manage-apps/what-is-single-sign-on)も参照してください。  <br/> |
|Power Apps  <br/> | Power Appsは、SharePoint リストや他のデータ アプリなどの既存のデータ ソースに接続できるモバイル デバイス用のフォーカスアプリです。 詳細については、[SharePoint Online の一覧とPower Appsページの Power App](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) の作成[](https://powerapps.microsoft.com/)に関するページを参照してください。  <br/> |
   
## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)
