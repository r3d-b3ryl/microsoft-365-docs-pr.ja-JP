---
title: Microsoft 365 管理者向ADアプリと Azure の統合アプリケーション
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
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
description: Azure Office 365 統合アプリAD登録および管理する方法について説明します。グローバル管理者レベルでのアプリ認証が可能です。
ms.openlocfilehash: 0b7392984b77b01abb0992fea5db62b80ed9fb6c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909776"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Microsoft 365 管理者向ADアプリと Azure の統合アプリケーション

統合アプリの管理には、アプリに対するユーザーの同意を管理 [する以外に多くの方法があります](../admin/misc/user-consent.md)。 Microsoft 365 REST API の登場により、ユーザーはアプリにメール、予定表、連絡先、ユーザー、グループ、ファイル、フォルダーなどの Microsoft 365 データへのアクセスを許可できます。 既定では、ユーザーは各アプリに個別にアクセス許可を付与する必要があります。 

ただし、グローバル管理者レベルでアプリを 1 回承認し、アプリ 起動ツールを通じて組織全体に展開する場合、これはうまく拡張できない。 これを行うには、アプリを Azure Active Directory (Azure Active Directory) に登録する必要AD。 Azure AD でアプリを登録する前に実行する必要があるいくつかの手順と、Microsoft 365 組織でアプリを管理するのに役立つ必要があるいくつかの背景情報があります。
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Azure AD Microsoft 365 管理者向けリソース

Microsoft 365 アプリを Azure サーバーで管理するには、この 2 つのタスクを実行するAD。
  
|前提条件|コメント|
|:-----|:-----|
|[無料の Azure サブスクリプションADする](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |Microsoft 365 の有料サブスクリプションには、Azure サービスへの無料サブスクリプションAD。 Azure ADを使用して、アプリを管理し、ユーザー アカウントとグループ アカウントを作成および管理できます。 Azure ADを使用するには、Azure portal に移動し [https://portal.azure.com](https://portal.azure.com) 、Microsoft 365 アカウントを使用してサインインします。  <br/> |
|[アプリに対するユーザーの同意を管理する](../admin/misc/user-consent.md) <br/> |サードパーティのアプリがユーザーの Microsoft 365 情報にアクセスし、Azure AD にアプリを登録するには、アプリに対するユーザーの同意を管理する必要があります。 たとえば、サードパーティ アプリを使用している場合、そのアプリが予定表へのアクセスと OneDrive フォルダーにあるファイルの編集のために権限を与えるように求めてくることがあります。  <br/> |
   
Microsoft 365 アプリを管理するには、Azure アプリのアプリに関する知識が必要AD。 これらの記事を使用して、必要な背景を提供します。
  
|記事|コメント|
|:-----|:-----|
|[Microsoft 365 アプリ 起動ツールに会う](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |アプリ 起動ツールを使いこなす場合は、アプリランチャーとは何か、どのように使うのか疑問に思う場合があります。 アプリ 起動ツールは、Microsoft 365 のどこからでもアプリにアクセスするために設計されています。  <br/> |
|[Office 365 管理 API の概要](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Microsoft 365 管理 API を使用すると、メール、予定表、連絡先、ユーザーとグループ、ファイル、フォルダーなど、Microsoft 365 データにアクセスできます。 <br/> |
|[Integrating applications in Azure AD](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Azure AD と統合されたアプリケーションと、アプリケーションを登録する方法、登録されたアプリケーションの背後にある概念を理解する方法、およびマルチテナント アプリケーションのブランド化ガイドラインについて説明します。  <br/> |
|[アプリ 起動ツールにカスタム タイルを追加する](/office365/admin/manage/customize-the-app-launcher)  <br/> |Microsoft 365 のアプリ 起動ツールを使用すると、ユーザーはアプリを簡単に見つけてアクセスできます。 この記事では、開発者がアプリをユーザーのアプリ 起動ツールに表示し、Microsoft 365 資格情報を使用してシングル サインオン (SSO) エクスペリエンスを提供する方法について説明します。  <br/> |
|[Azure AD統合チュートリアル](/azure/active-directory/saas-apps/tutorial-list) <br/> |これらのチュートリアルの目的は、サードパーティの SaaS アプリケーション用に Azure AD SSO を構成する方法を示す方法です。  <br/> |
|[Azure AD の認証シナリオ](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure AD では、OAuth 2.0 や OpenID Connect などの業界標準プロトコルや、さまざまなプラットフォーム用のオープン ソース ライブラリをサポートして、ID をサービスとして提供することで、開発者の認証を簡素化します。 このドキュメントは、Azure ADサポートするさまざまなシナリオを理解し、開始する方法を示します。  <br/> |
|[アプリケーション アクセス](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure ADは、サービスとしての今日の一般的なソフトウェア (SaaS) アプリケーションの多くを簡単に統合できます。 ID とアクセスの管理を提供し、ユーザーが持っているアプリケーション アクセスと、SSO を使用してアプリケーションにアクセスできる場所を検出できるアクセス パネルを提供します。 この記事では、関連するリソースへのリンクを提供し、Azure AD のアプリケーション アクセス拡張機能と、そのリソースに貢献する方法について説明します。  <br/> |
|[365 エクスペリエンスOfficeカスタマイズする](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Microsoft 365 アプリ 起動ツールでアプリを追加または削除することで、毎日使用するアプリにすばやくアクセスできます。  <br/> |