---
title: 無料の Azure Active Directory Domain Services サブスクリプションを使用する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: d104fb44-1c42-4541-89a6-1f67be22e4ad
description: 組織の有料サブスクリプションに含まれる、Azure Active Directory にアクセスする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 43c9c03af74d4edc1fb6c762c9ca89594a907920
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819287"
---
# <a name="use-your-free-azure-active-directory-subscription"></a>無料の Azure Active Directory Domain Services サブスクリプションを使用する

If your organization has a paid subscription to Microsoft 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite, or other Microsoft services, you have a free subscription to Microsoft Azure Active Directory. You and other admins can use Azure AD to create and manage user and group accounts. To use Azure AD, just go to the Azure portal and sign in to your account.

## <a name="open-a-private-browsing-session"></a>プライベート ブラウザー セッションを開く

Use a private browsing session (not a regular session) to access the Azure portal (in step 1 below) because this prevents the credentials that you're currently logged on with from being passed to Azure. To open an private browsing session:

- Microsoft Edge (レガシ バージョン)、Internet Explorer、または Mozilla FireFox では、`CTRL+SHIFT+P` を押します。

- Microsoft Edge (最新バージョン) または Google Chrome では、`CTRL+SHIFT+N` を押します。

## <a name="access-azure-active-directory"></a>Azure Active Directory にアクセスする

1. [portal.azure.com](https://portal.azure.com) に移動し、自分の職場または学校のアカウントを使用してサインインします。

2. Azure portal の左側のナビゲーション ウィンドウで **Azure Active Directory** をクリックします。

    ![Azure portal の左側のナビゲーション ウィンドウで [Azure Active Directory] をクリックします。](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    **Azure Active Directory** 管理センターが表示されます。

## <a name="more-information"></a>More information

- 無料の Azure Active Directory サブスクリプションには、サインイン アクティビティのレポートは含まれません。 (データ侵害が発生した場合に役立つ可能性がある) サインイン アクティビティを記録するには、Azure Active Directory Premium サブスクリプションが必要です。 詳細については、[Azure AD がデータを保存する期間](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data)を参照してください。

- Microsoft 365 管理センターから ** Azure Active Directory** 管理センターにアクセスすることもできます。 Microsoft 365 管理センターの左側のナビゲーションウィンドウで、[**管理センター**]、[\>** Azure Active Directory**] の順にクリックします。

- ユーザーとグループの管理や、その他のディレクトリ管理タスクの実行の詳細については、「[Azure AD Directory の管理](https://docs.microsoft.com/azure/active-directory/active-directory-administer)」を参照してください。
