---
title: 管理者向け統合AD Azure Microsoft 365
ms.author: kvice
author: kelleyvice-msft
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
description: Azure AD で統合アプリを登録および管理する **AD、Azure** AD DC 管理者、またはグローバル管理者レベルでアプリの承認を許可する方法について **説明** します。 Office 365
ms.openlocfilehash: ccf1e16e7e0307499e515eb3691c865d49801412
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215983"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>管理者向け統合AD Azure Microsoft 365

統合アプリの管理には、アプリに対するユーザーの同意を管理 [する以外に多くの方法があります](../admin/misc/user-consent.md)。 Microsoft 365 REST API の登場により、ユーザーはアプリにメール、予定表、連絡先、ユーザー、グループ、ファイル、フォルダーなどの Microsoft 365 データへのアクセス権を付与できます。 既定では、ユーザーは各アプリに個別にアクセス許可を付与する必要があります。 

ただし **、Azure AD DC** 管理者、またはグローバル管理者レベルでアプリを 1 回承認し、アプリ起動ツールを通じて組織全体に展開する場合、これはうまく拡張できない。 これを行うには、アプリをアプリ (Azure Azure Active Directory) に登録AD。 Azure AD でアプリを登録する前に実行する必要があるいくつかの手順と、Microsoft 365 組織でアプリを管理するのに役立つ必要があるいくつかの背景情報があります。
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Azure AD管理者Microsoft 365リソース

Azure アプリでアプリを管理するには、この 2 つのMicrosoft 365する必要AD。
  
|前提条件|コメント|
|:-----|:-----|
|[無料の Azure サブスクリプションADする](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |すべての有料サブスクリプションには、Microsoft 365 Azure サービスへの無料サブスクリプションAD。 Azure ADを使用して、アプリを管理し、ユーザー アカウントとグループ アカウントを作成および管理できます。 Azure ADを使用するには、Azure portal に移動し、アカウントを使用してサインインMicrosoft 365 [https://portal.azure.com](https://portal.azure.com) します。  <br/> |
|[アプリに対するユーザーの同意を管理する](../admin/misc/user-consent.md) <br/> |サードパーティアプリがユーザー情報にアクセスし、Azure Microsoft 365 にアプリを登録するには、アプリに対するユーザーの同意を管理する必要AD。 たとえば、サードパーティ アプリを使用している場合、そのアプリが予定表へのアクセスと OneDrive フォルダーにあるファイルの編集のために権限を与えるように求めてくることがあります。  <br/> |
   
アプリをMicrosoft 365するには、Azure アプリのアプリに関する知識が必要AD。 これらの記事を使用して、必要な背景を提供します。
  
|記事|コメント|
|:-----|:-----|
|[アプリ起動ツールMicrosoft 365する](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |アプリ 起動ツールを使いこなす場合は、アプリランチャーとは何か、どのように使うのか疑問に思う場合があります。 アプリ 起動ツールは、アプリのどこからでもアプリにアクセスMicrosoft 365。  <br/> |
|[Office 365管理 API の概要](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Microsoft 365管理 API を使用すると、Microsoft 365 データ (メール、予定表、連絡先、ユーザーとグループ、ファイル、フォルダーなど) にアクセスできます。 <br/> |
|[Integrating applications in Azure AD](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Azure AD と統合されたアプリケーションと、アプリケーションを登録する方法、登録されたアプリケーションの背後にある概念を理解する方法、およびマルチテナント アプリケーションのブランド化ガイドラインについて説明します。  <br/> |
|[アプリ 起動ツールにカスタム タイルを追加する](/office365/admin/manage/customize-the-app-launcher)  <br/> |アプリ起動ツールはMicrosoft 365ユーザーが簡単にアプリを見つけてアクセスできます。 この記事では、開発者がアプリをユーザーのアプリ 起動ツールに表示し、Microsoft 365 資格情報を使用してシングル サインオン (SSO) エクスペリエンスを提供する方法について説明します。  <br/> |
|[Azure AD統合チュートリアル](/azure/active-directory/saas-apps/tutorial-list) <br/> |これらのチュートリアルの目的は、サードパーティの SaaS アプリケーション用に Azure AD SSO を構成する方法を示す方法です。  <br/> |
|[Azure AD の認証シナリオ](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure AD では、OAuth 2.0 や OpenID Connect などの業界標準のプロトコルや、さまざまなプラットフォーム用のオープン ソース ライブラリをサポートして、ID をサービスとして提供することで、開発者の認証を簡素化します。 このドキュメントは、Azure ADサポートするさまざまなシナリオを理解し、開始する方法を示します。  <br/> |
|[アプリケーション アクセス](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure ADは、サービスとしての今日の一般的なソフトウェア (SaaS) アプリケーションの多くを簡単に統合できます。 ID とアクセスの管理を提供し、ユーザーが持っているアプリケーション アクセスと、SSO を使用してアプリケーションにアクセスできる場所を検出できるアクセス パネルを提供します。 この記事では、関連するリソースへのリンクを提供し、Azure AD のアプリケーション アクセス拡張機能と、そのリソースに貢献する方法について説明します。  <br/> |
|[ユーザーエクスペリエンスOffice 365カスタマイズする](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |アプリ 起動ツールでアプリを追加または削除することで、毎日使用するアプリにすばやくMicrosoft 365できます。  <br/> |
