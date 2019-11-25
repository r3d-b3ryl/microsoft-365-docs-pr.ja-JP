---
title: Office 365 で無料の Azure Active Directory サブスクリプションを使用する
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
description: 組織の Office 365 の有料サブスクリプションに含まれる、Azure Active Directory にアクセスする方法について説明します。
ms.openlocfilehash: bf958eebfbcc67d4b344452636b1a84396296f3a
ms.sourcegitcommit: ab986f0d8cf074fae41e77bfdc2895c64fed9091
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2019
ms.locfileid: "39218822"
---
# <a name="use-your-free-azure-active-directory-subscription-in-office-365"></a>Office 365 で無料の Azure Active Directory サブスクリプションを使用する

組織が Office 365、Microsoft Dynamics CRM Online、Enterprise Mobility Suite、その他の Microsoft サービスの有料サブスクリプションを保有している場合、Microsoft Azure Active Directory の無料サブスクリプションを利用できます。管理者であれば、Azure AD を使用してユーザー アカウントとグループ アカウントを作成および管理できます。Azure AD を使用するには、Azure portal にアクセスし、Office 365 アカウントを使ってサインインします。

## <a name="before-you-begin"></a>はじめに

現在ログオンしている資格情報が Azure に渡されないようにするため、プライベート ブラウズ セッション (通常のセッションではありません) を使用して Azure portal にアクセスします (以下の手順 1)。Internet Explorer で InPrivate ブラウズ セッションまたは Mozilla FireFox でプライベート ブラウズ セッションを開くには、CTRL + SHIFT + P キーを押してください。Google Chrome でプライベート ブラウズ セッションを開くには (シークレット ウィンドウと呼ばれます)、CTRL + SHIFT + N キーを押します。

## <a name="access-azure-active-directory"></a>Azure Active Directory にアクセスする

1. [portal.azure.com](https://portal.azure.com) にアクセスし、Office 365 の職場または学校のアカウントでサインインします。

2. Azure portal の左側のナビゲーション ウィンドウで **Azure Active Directory** をクリックします。

    ![Azure portal の左側のナビゲーション ウィンドウで [Azure Active Directory] をクリックします。](media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    **Azure Active Directory** 管理センターが表示されます。

## <a name="more-information"></a>More information

- 無料の Azure Active Directory サブスクリプションには、サインイン アクティビティのレポートは含まれません。 (データ侵害が発生した場合に役立つ可能性がある) サインイン アクティビティを記録するには、Azure Active Directory Premium サブスクリプションが必要です。 詳細については、[Azure AD がデータを保存する期間](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data)を参照してください。

- Microsoft 365 管理センターから ** Azure Active Directory** 管理センターにアクセスすることもできます。 Microsoft 365 管理センターの左側のナビゲーションウィンドウで、[**管理センター**]、[\>** Azure Active Directory**] の順にクリックします。

- ユーザーとグループの管理や、その他のディレクトリ管理タスクの実行の詳細については、「[Azure AD Directory の管理](https://docs.microsoft.com/azure/active-directory/active-directory-administer)」を参照してください。
