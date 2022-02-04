---
title: Azure と Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
description: パスワードMicrosoft 365シングル サインオンAzure ADオンプレミス環境と同期する場合は、パスワードとパスワードを統合します。
---

# <a name="azure-integration-with-microsoft-365"></a>Azure と Microsoft 365

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 (Azure Active Directory) Azure ADを使用して、ユーザー ID を管理します。 Microsoft 365 サブスクリプションには無料の Azure AD サブスクリプションが含まれるので、オンプレミスの Active Directory ドメイン サービス (AD DS) を統合してユーザー アカウントとパスワードを同期したり、シングル サインオンを設定したりできます。 また、高度な機能を購入して、アカウントの管理を向上することもできます。
  
Azure AD、統合アプリの管理など、サブスクリプションの拡張とカスタマイズに使用できるその他のMicrosoft 365があります。
  
ガイド付きセットアップAzure AD構成エクスペリエンスには、Azure AD 展開アドバイザーを使用できます (Microsoft 365 管理センターにサインインする必要Microsoft 365)。

 - [Azure AD Connectアドバイザー](https://aka.ms/aadconnectpwsync)
 - [AD FS 展開アドバイザー](https://aka.ms/adfsguidance)
 - [Azure ADセットアップ ガイド](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure ADエディションとMicrosoft 365 ID 管理

有料サブスクリプションを利用している場合Microsoft 365無料のサブスクリプションAzure ADがあります。 ユーザー アカウントとグループ Azure ADを作成および管理するには、ユーザー アカウントとグループ アカウントを使用します。 このサブスクリプションをアクティブ化するには、1 回の登録を完了する必要があります。 その後、サーバーからAzure ADにアクセスMicrosoft 365 管理センター。 

無料のサブスクリプションを登録するAzure ADについては、「無料のサブスクリプションをAzure AD[してください](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)。 azure.microsoft.com に直接アクセスしてサインアップしたり、Microsoft 365 で無料の Azure AD サブスクリプションとは別の Microsoft Azure の試用版または有料サブスクリプションを利用したりします。 
  
無料サブスクリプションを使用すると、オンプレミスのディレクトリと同期し、シングル サインオンを設定し、Salesforce、DropBox などのサービス アプリケーションとして多くのソフトウェアと同期できます。
  
DS 機能、双方向AD、その他の管理機能を強化する場合は、無料サブスクリプションを有料のプレミアム サブスクリプションにアップグレードできます。 詳細については、「Azure Active Directory[」を参照してください](https://azure.microsoft.com/pricing/details/active-directory/)。
  
ID モデルと id モデルMicrosoft 365 Azure AD詳細については、「Microsoft 365[」を参照してください](deploy-identity-solution-identity-model.md)。
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>テナントの機能を拡張Microsoft 365する

|**機能**|**説明**|
|:-----|:-----|
|統合アプリ  <br/> |メール、予定表、連絡先、ユーザー、グループ、ファイル、フォルダーなど、Microsoft 365データへのアクセスを個々のアプリに付与できます。 また、DC 管理者またはグローバル管理者レベルAzure ADでこれらのアプリを承認し、アプリを管理者に登録して会社全体で利用Azure AD。 詳細については、「[Integrated Apps and Azure AD管理者Microsoft 365参照してください](integrated-apps-and-azure-ads.md)。<br/> 詳細については、「[管理者の役割について](/microsoft-365/admin/add-users/about-admin-roles?)」を参照してください。 <br/> 「シングル [サインオン」も参照してください](/azure/active-directory/manage-apps/what-is-single-sign-on)。  <br/> |
|Power アプリ  <br/> | Power Appsリストや他のデータ アプリなど、既存のデータ ソースに接続できるモバイル デバイス向SharePointアプリです。 詳細[については、「Create a Power App for a list in SharePoint」](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab)および「Power Apps[ページ」](https://powerapps.microsoft.com/)を参照してください。  <br/> |
   
## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)
