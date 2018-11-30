---
title: '手順 10: ユーザー サインインを簡素化する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD シームレス シングル サインオン (シームレス SSO) について理解し、構成します。
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869542"
---
# <a name="step-10-simplify-user-sign-in"></a>手順 10: ユーザー サインインを簡素化する

*この手順はハイブリッド環境でオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

この手順では、Azure Active Directory シームレス シングル サインオン (Azure AD シームレス SSO) を設定し、Azure AD ユーザー アカウントを使用するサービスにユーザーがパスワードを入力せずに (また多くの場合、ユーザー名を入力せずに) サインインできるようにします。これにより、ID フェデレーション サーバーなどのオンプレミス コンポーネントを追加せずに、ユーザーが Office 365 などのクラウドベース アプリケーションに簡単にアクセスできるようになります。

Azure AD Connect ツールを使用して Azure AD シームレス SSO を構成します。

「[Azure Active Directory シームレス シングル サインオン: クイック スタート](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)」を参照してください。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: Azure AD シームレス シングル サインオン](single-sign-on-m365-ent-test-environment.md) |
|||

中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-sso)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [Office 365 サインイン ページをカスタマイズする](identity-customize-office-365-sign-in.md) |

