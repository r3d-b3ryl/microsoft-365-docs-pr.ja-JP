---
title: リスクの高いユーザーの表示と管理
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 管理サービス プロバイダー (MSP) が Microsoft 365 Lighthouseを使用する場合は、リスクの高いユーザーを表示および管理する方法について説明します。
ms.openlocfilehash: 708fc0576c85d9b8511ac6b31ed0398fae1b20d3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331008"
---
# <a name="view-and-manage-risky-users"></a>リスクの高いユーザーの表示と管理

Microsoft は、毎日何兆ものユーザー サインイン信号を収集して分析します。 これらのシグナルは、優れたユーザー サインイン動作パターンを構築し、潜在的に危険なサインイン試行を特定するために使用されます。 Azure Active Directory (Azure AD) Identity Protection は、これらのシグナルを使用して、ユーザーのサインイン試行を確認し、疑わしいアクティビティがある場合はアクションを実行します。

Microsoft 365 Lighthouse管理テナント全体でリスクの高いユーザーを 1 つのビューで表示することで、Azure AD Id Protection によって検出されたリスクを管理できます。 リスクの高いユーザーは、パスワードをリセットするか、ユーザーが自分のアカウントにサインインMicrosoft 365できます。 また、分析情報を表示して、ユーザーのリスクをよりよく理解し、次の手順を決定できます。

Azure AD Id Protection は、次を含む多くの種類のリスクを識別します。

- 漏えいした資格情報
- 匿名 IP の使用
- 非聖書的な旅行
- 感染したデバイスからのサインイン
- 疑わしいアクティビティを持つ IP アドレスからサインインする
- 見慣れない場所からのサインイン

## <a name="before-you-begin"></a>始める前に

ユーザーが危険なユーザーリストに表示される前に、次の条件を満たしている必要があります。

- 顧客テナントには、ユーザーごとに Azure AD Premium ライセンスが必要です。 ID 保護をサポートするライセンスのAzure AD詳細については、「[What is Identity Protection」を参照してください。](/azure/active-directory/identity-protection/overview-identity-protection)

- 顧客テナントは Microsoft 365 Lighthouse 内でアクティブである必要があります。 テナントがアクティブかどうかを確認するには、「テナント[」ページMicrosoft 365 Lighthouseを参照してください](m365-lighthouse-tenant-list-overview.md)。

## <a name="review-detected-risks-and-take-action"></a>検出されたリスクを確認し、アクションを実行する

Id Protection Azure ADでは、リスク検出には、ユーザー アカウントに関連する特定された疑わしいアクションが含Azure AD。

1. Lighthouse の左側のナビゲーション ウィンドウで、**[ユーザー]** を選択します。

2. [危険な **ユーザー] タブを選択** します。

3. リスク状態が危険な状態の一覧のユーザー **を確認します**。

4. [ **リスク検出の表示] を** 選択して、ユーザーごとに検出されたリスクに関する詳細情報を取得します。 リスクの種類と検出の詳細については、「リスク [とは」を参照してください](/azure/active-directory/identity-protection/concept-identity-protection-risks)。

5. ユーザーごとにリスク検出を評価し、必要に応じて次のいずれかのアクションを選択します。

    - パスワードのリセット – ユーザー パスワードを変更またはリセットします。

    - [サインインをブロックする] - このユーザーとしてサインインするユーザーを防止します。

    - ユーザーの侵害を確認する - リスク状態を確認済み侵害に設定します。

    - ユーザー リスクの却下 - リスク状態を [却下] に設定します。

## <a name="take-action-on-multiple-user-accounts-at-once"></a>複数のユーザー アカウントに対して一度にアクションを実行する

影響を受ける複数のユーザーに対して一度にアクションを実行するには、次の操作を行います。

1. [危険な **ユーザー] タブ** で、アクションを実行するユーザーのセットを選択します。

2. 実行する次のいずれかのアクションを選択します。

    - パスワードのリセット

    - サインインをブロックする

    - ユーザーが侵害されたのを確認する

    - ユーザー リスクの却下

> [!NOTE]
> 管理している組織にユーザー ライセンスAzure AD Premium P2場合は、ユーザー リスクベースの条件付きアクセス ポリシーを有効にしてください。 詳細については、「条件付きアクセス [: ユーザー リスクベースの条件付きアクセス」を参照してください](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk-user)。

## <a name="related-content"></a>関連コンテンツ
[チュートリアル: ユーザー サインインのリスク](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa)検出を使用して、多要素認証Azure ADパスワードの変更をトリガーする (記事)\
[リスクとは](/azure/active-directory/identity-protection/concept-identity-protection-risks) (記事) \
[リスクを修復し、ユーザーのブロックを解除する](/azure/active-directory/identity-protection/howto-identity-protection-remediate-unblock) (記事)
