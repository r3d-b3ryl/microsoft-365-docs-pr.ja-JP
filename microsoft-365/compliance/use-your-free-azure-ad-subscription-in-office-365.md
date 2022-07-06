---
title: 無料の Azure Active Directory Domain Services サブスクリプションを使用する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: d104fb44-1c42-4541-89a6-1f67be22e4ad
description: 組織の有料サブスクリプションに含まれる、Azure Active Directory にアクセスする方法について説明します。
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
ms.openlocfilehash: 2d6e274f286893adaeecb81b519b72dc5ba7927a
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66625943"
---
# <a name="use-your-free-azure-active-directory-subscription"></a>無料の Azure Active Directory Domain Services サブスクリプションを使用する

組織が Microsoft 365、Microsoft Dynamics CRM Online、Enterprise Mobility Suite、その他の Microsoft サービスの有料サブスクリプションを保有している場合、Microsoft Azure Active Directory の無料サブスクリプションを利用できます。管理者であれば、Azure AD を使用してユーザー アカウントとグループ アカウントを作成および管理できます。Azure AD を使用するには、Azure portal にアクセスし、アカウンにサインインします。

## <a name="open-a-private-browsing-session"></a>プライベート ブラウザー セッションを開く

(通常のセッションではなく) プライベート ブラウジング セッションを使用して、Azure portal (以下の手順 1 参照) にアクセスします。現在のログオンに使用している資格情報が Azure に渡されません。プライベート ブラウジング セッションを開始するには:

- Microsoft Edge (レガシ バージョン)、Internet Explorer、または Mozilla FireFox では、`CTRL+SHIFT+P` を押します。

- Microsoft Edge (最新バージョン) または Google Chrome では、`CTRL+SHIFT+N` を押します。

## <a name="access-azure-active-directory"></a>Azure Active Directory にアクセスする

1. [portal.azure.com](https://portal.azure.com) に移動し、自分の職場または学校のアカウントを使用してサインインします。

2. Azure portal の左側のナビゲーション ウィンドウで **Azure Active Directory** をクリックします。

    ![Azure portal の左側のナビゲーション ウィンドウで [Azure Active Directory] をクリックします。](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    **Azure Active Directory** 管理センターが表示されます。

## <a name="more-information"></a>詳細情報

- 無料の Azure Active Directory サブスクリプションには、サインイン アクティビティのレポートは含まれません。 (データ侵害の際に役立つ可能性がある) サインイン アクティビティを記録するには、Azure Active Directory Premium サブスクリプションが必要です。 詳細については、[Azure AD がデータを保存する期間](/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data)を参照してください。

- Microsoft 365 管理センターから **Azure Active Directory** 管理センターにアクセスすることもできます。Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、**管理センター** \> [**Azure Active Directory**](https://go.microsoft.com/fwlink/p/?linkid=2067268) をクリックします。

- ユーザーとグループの管理や、その他のディレクトリ管理タスクの実行の詳細については、「[Azure AD Directory の管理](/azure/active-directory/active-directory-administer)」を参照してください。