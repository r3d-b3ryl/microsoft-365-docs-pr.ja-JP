---
title: Microsoft 365管理者向けの統合アプリとAzure AD
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: landing-page
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection: M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: cb2250e3-451e-416f-bf4e-363549652c2a
description: Azure ADで統合アプリOffice 365登録および管理し、**Azure AD DC 管理者** または **グローバル管理者** レベルでアプリの承認を許可する方法について説明します。
ms.openlocfilehash: 63d88d5b39dd88fafa9bb874d7d0a9df11f89462
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091195"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Microsoft 365管理者向けの統合アプリとAzure AD

統合アプリの管理は、アプリに対する [ユーザーの同意を管理する](../admin/misc/user-consent.md)だけではありません。 Microsoft 365 REST API の出現により、ユーザーはアプリにメール、予定表、連絡先、ユーザー、グループ、ファイル、フォルダーなどのMicrosoft 365 データへのアクセスを許可できます。 既定では、ユーザーは各アプリに個別にアクセス許可を付与する必要があります。 

ただし、Azure AD **DC 管理者** または **グローバル管理者** レベルで 1 回アプリを承認し、アプリ起動ツールを使用して組織全体に展開する場合、これは適切にスケーリングされません。 これを行うには、Azure Active Directory (Azure AD) にアプリを登録する必要があります。 Azure ADにアプリを登録するには、いくつかの手順を実行する必要があります。また、Microsoft 365組織内のアプリの管理に役立ついくつかの背景情報が必要です。
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Microsoft 365管理者向けのAzure AD リソース

Azure ADでMicrosoft 365 アプリを管理するには、この 2 つのタスクを実行する必要があります。
  
|前提条件|Comments|
|:-----|:-----|
|[無料のAzure AD サブスクリプションを使用する](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |Microsoft 365のすべての有料サブスクリプションには、Azure ADへの無料サブスクリプションが付属しています。 Azure ADを使用してアプリを管理し、ユーザー アカウントとグループ アカウントを作成および管理できます。 Azure ADを使用するには、Azure portalに[https://portal.azure.com](https://portal.azure.com)移動し、Microsoft 365 アカウントを使用してサインインするだけです。  <br/> |
|[アプリに対するユーザーの同意を管理する](../admin/misc/user-consent.md) <br/> |サード パーティのアプリがユーザー Microsoft 365情報にアクセスできるようにアプリに対するユーザーの同意を管理し、アプリをAzure ADに登録する必要があります。 たとえば、サードパーティ アプリを使用している場合、そのアプリが予定表へのアクセスと OneDrive フォルダーにあるファイルの編集のために権限を与えるように求めてくることがあります。  <br/> |
   
Microsoft 365 アプリを管理するには、Azure ADのアプリに関する知識が必要です。 これらの記事を使用して、必要な背景を提供します。
  
|記事|Comments|
|:-----|:-----|
|[Microsoft 365 アプリ起動ツールを確認する](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |アプリ起動ツールを初めて使用する場合は、アプリの概要と使用方法が気になる場合があります。 アプリ起動ツールは、Microsoft 365のどこからでもアプリにアクセスできるように設計されています。  <br/> |
|[Office 365管理 API の概要](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Microsoft 365管理 API を使用すると、メール、予定表、連絡先、ユーザー、グループ、ファイル、フォルダーなど、Microsoft 365 データへのアクセスを提供できます。 <br/> |
|[Azure ADでのアプリケーションの統合](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Azure ADと統合されているアプリケーションと、アプリケーションを登録する方法、登録済みのアプリケーションの背後にある概念を理解する方法、マルチテナント アプリケーションのブランド化ガイドラインについて説明します。  <br/> |
|[アプリ起動ツールにカスタム タイルを追加する](/office365/admin/manage/customize-the-app-launcher)  <br/> |Microsoft 365のアプリ起動ツールを使用すると、ユーザーがアプリを簡単に見つけてアクセスできるようになります。 この記事では、開発者がアプリをユーザーのアプリ起動ツールに表示し、Microsoft 365資格情報を使用してシングル サインオン (SSO) エクスペリエンスを提供する方法について説明します。  <br/> |
|[Azure AD統合チュートリアル](/azure/active-directory/saas-apps/tutorial-list) <br/> |これらのチュートリアルの目的は、サード パーティの SaaS アプリケーションの SSO Azure AD構成する方法について説明することです。  <br/> |
|[Azure AD の認証シナリオ](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure ADは、OAuth 2.0 や OpenID Connectなどの業界標準のプロトコルをサポートし、さまざまなプラットフォーム用のオープンソース ライブラリをサポートすることで、サービスとしての ID を提供することで開発者の認証を簡素化し、コーディングを迅速に開始できます。 このドキュメントでは、Azure ADがサポートするさまざまなシナリオを理解し、作業を開始する方法について説明します。  <br/> |
|[アプリケーション へのアクセス](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure ADにより、現在普及している多くのサービスとしてのソフトウェア (SaaS) アプリケーションに簡単に統合できます。 ID とアクセス管理を提供し、ユーザーが持つアプリケーション アクセスを検出し、SSO を使用してアプリケーションにアクセスできる場所をユーザーに提供するアクセス パネルを提供します。 この記事では、関連リソースへのリンクを提供します。これにより、Azure ADのアプリケーション アクセスの機能強化の詳細と、それらに貢献する方法を確認できます。  <br/> |
|[Office 365エクスペリエンスをカスタマイズする](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Microsoft 365 アプリ起動ツールでアプリを追加または削除することで、毎日使用しているアプリにすばやくアクセスできます。  <br/> |
