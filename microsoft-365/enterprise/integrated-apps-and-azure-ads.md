---
title: 管理者向けAzure ADアプリMicrosoft 365統合
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
description: Office 365 Azure AD で統合アプリを登録および管理する方法についてAzure AD **DC** 管理者またはグローバル管理者レベルでアプリの承認を許可する方法について **学習** します。
ms.openlocfilehash: ddb22c6e1be3d337fe7b54f27cae6a197f823c71
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681262"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>管理者向けAzure ADアプリMicrosoft 365統合

統合アプリの管理には、アプリに対するユーザーの同意 [を管理する以外に多くの方法があります](../admin/misc/user-consent.md)。 Microsoft 365 REST API の登場により、ユーザーはアプリにメール、予定表、連絡先、ユーザー、グループ、ファイル、フォルダーなどの Microsoft 365 データへのアクセス権を付与できます。 既定では、ユーザーは各アプリに個別にアクセス許可を付与する必要があります。 

**ただし、Azure AD DC** 管理者またはグローバル管理者レベルでアプリを 1 回承認し、アプリ 起動ツールを通じて組織全体に展開する場合、これはうまく拡張できない。 これを行うには、アプリをアプリに登録する必要Azure Active Directory (Azure AD)。 Azure AD でアプリを登録する前に実行する必要があるいくつかの手順と、Microsoft 365 組織内のアプリを管理するのに役立つ必要があるいくつかの背景情報があります。
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Azure AD管理者向けMicrosoft 365リソース

この 2 つのタスクを実行してから、アプリを管理する前に、Microsoft 365アプリAzure AD。
  
|前提条件|コメント|
|:-----|:-----|
|[無料のサブスクリプションAzure ADする](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |すべての有料サブスクリプションには、Microsoft 365無料のサブスクリプションが付属Azure AD。 アプリを管理Azure AD、ユーザー アカウントとグループ アカウントを作成および管理できます。 アカウントをAzure ADするには、Azure portal [https://portal.azure.com](https://portal.azure.com) に移動し、アカウントを使用してサインインMicrosoft 365します。  <br/> |
|[アプリに対するユーザーの同意を管理する](../admin/misc/user-consent.md) <br/> |サードパーティのアプリがユーザー情報にアクセスし、アプリをアプリに登録するには、アプリに対するユーザー Microsoft 365を管理する必要Azure AD。 たとえば、サードパーティ アプリを使用している場合、そのアプリが予定表へのアクセスと OneDrive フォルダーにあるファイルの編集のために権限を与えるように求めてくることがあります。  <br/> |
   
アプリをMicrosoft 365するには、アプリに関する知識が必要Azure AD。 これらの記事を使用して、必要な背景を提供します。
  
|記事|コメント|
|:-----|:-----|
|[アプリ起動ツールMicrosoft 365する](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |アプリ 起動ツールを使いこなす場合は、アプリランチャーとは何か、どのように使うのか疑問に思う場合があります。 アプリ 起動ツールは、アプリのどこからでもアプリにアクセスMicrosoft 365。  <br/> |
|[Office 365管理 API の概要](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Microsoft 365管理 API を使用すると、Microsoft 365 データ (メール、予定表、連絡先、ユーザーとグループ、ファイル、フォルダーなど) にアクセスできます。 <br/> |
|[アプリケーションの統合Azure AD](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Azure AD と統合されたアプリケーションについて、およびアプリケーションを登録する方法、登録されたアプリケーションの背後にある概念を理解する方法、およびマルチテナント アプリケーションのブランド化ガイドラインについて説明します。  <br/> |
|[アプリ 起動ツールにカスタム タイルを追加する](/office365/admin/manage/customize-the-app-launcher)  <br/> |アプリ起動ツールはMicrosoft 365ユーザーが簡単にアプリを見つけてアクセスできます。 この記事では、開発者がアプリをユーザーのアプリ 起動ツールに表示し、Microsoft 365 資格情報を使用してシングル サインオン (SSO) エクスペリエンスを提供する方法について説明します。  <br/> |
|[Azure ADのチュートリアル](/azure/active-directory/saas-apps/tutorial-list) <br/> |これらのチュートリアルの目的は、サードパーティの SaaS アプリケーションAzure AD SSO を構成する方法を示す方法です。  <br/> |
|[Azure AD の認証シナリオ](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure ADは、OAuth 2.0 や OpenID Connect などの業界標準プロトコルと、さまざまなプラットフォームのオープン ソース ライブラリをサポートして、ID をサービスとして提供することで、開発者の認証を簡素化します。 このドキュメントでは、サポートされるさまざまなシナリオAzure AD理解し、開始する方法を示します。  <br/> |
|[アプリケーション アクセス](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure ADサービス (SaaS) アプリケーションとして現在人気のある多くのソフトウェアに簡単に統合できます。 ID とアクセスの管理を提供し、ユーザーが持っているアプリケーション アクセスと、SSO を使用してアプリケーションにアクセスできる場所を検出できるアクセス パネルを提供します。 この記事では Azure AD、関連するリソースへのリンクを提供します。  <br/> |
|[ユーザーエクスペリエンスOffice 365カスタマイズする](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |アプリ 起動ツールでアプリを追加または削除することで、毎日使用するアプリにすばやくMicrosoft 365できます。  <br/> |
