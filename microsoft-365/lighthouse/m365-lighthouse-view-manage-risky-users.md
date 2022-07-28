---
title: Microsoft 365 Lighthouseでリスクの高いユーザーを表示および管理する
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: ragovind
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
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、危険なユーザーを表示および管理する方法について説明します。
ms.openlocfilehash: 6f3fdaca1b89561e623d195faa4804c431e43a69
ms.sourcegitcommit: 23a53b5c5e372a2a7ad5e175850224d3d464f6dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2022
ms.locfileid: "67055836"
---
# <a name="view-and-manage-risky-users-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseでリスクの高いユーザーを表示および管理する

Microsoft では、毎日何兆ものユーザー サインインシグナルを収集し、分析しています。 これらのシグナルは、適切なユーザー サインイン動作パターンを構築し、潜在的な危険なサインイン試行を特定するために使用されます。 Azure Active Directory (Azure AD) Identity Protection では、これらのシグナルを使用してユーザー のサインイン試行を確認し、疑わしいアクティビティがある場合はアクションを実行します。

Microsoft 365 Lighthouseは、すべてのマネージド テナントに危険なユーザーを 1 つのビューで表示することで、Azure AD Identity Protection によって検出されたリスクを管理するのに役立ちます。 パスワードをリセットするか、Microsoft 365 アカウントへのサインインをブロックすることで、危険なユーザーを迅速にセキュリティで保護できます。 分析情報を表示して、ユーザーのリスクをよりよく理解し、次の手順を決定することもできます。

Azure AD Identity Protection は、次のような多くの種類のリスクを識別します。

- 漏えいした資格情報
- 匿名 IP の使用
- 非定型旅行
- 感染したデバイスからサインインする
- 疑わしいアクティビティを使用して IP アドレスからサインインする
- なじみのない場所からサインインする

## <a name="before-you-begin"></a>はじめに

危険なユーザーの一覧にユーザーを表示するには、次の条件を満たす必要があります。

- 顧客テナントには、ユーザーごとに Azure AD Premium ライセンスが必要です。 Azure AD Identity Protection をサポートするライセンスの詳細については、「Identity Protection とは[」を](/azure/active-directory/identity-protection/overview-identity-protection)参照してください。

- 顧客テナントは Microsoft 365 Lighthouse 内でアクティブである必要があります。 テナントがアクティブかどうかを確認するには、[Microsoft 365 LighthouseのWindows 365 (クラウド PC) ページの概要に関するページを](m365-lighthouse-tenant-list-overview.md)参照してください。

## <a name="review-detected-risks-and-take-action"></a>検出されたリスクを確認し、アクションを実行する

Azure AD Identity Protection では、リスク検出には、Azure AD のユーザー アカウントに関連する特定された疑わしいアクションが含まれます。

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **ユーザー** > **リスクの高いユーザー**] を選択します。

2. [ **危険なユーザー** ] タブで、リスク状態が **[リスク** あり] の一覧のユーザーを確認します。

3. [ **リスク検出の表示** ] を選択して、各ユーザーについて検出されたリスクに関する詳細情報を取得します。 リスクの種類と検出の詳細については、「 [リスクとは」](/azure/active-directory/identity-protection/concept-identity-protection-risks)を参照してください。

4. 各ユーザーについて、リスク検出を評価し、必要に応じて次のいずれかのアクションを選択します。

    - パスワードのリセット – ユーザー パスワードを変更またはリセットします。

    - サインインをブロックする - このユーザーとしてだれかがサインインできないようにします。

    - 侵害されたユーザーを確認します。 リスク状態を、侵害が確認された状態に設定します。

    - ユーザー リスクを無視する - リスク状態を無視に設定します。

## <a name="take-action-on-multiple-user-accounts-at-once"></a>複数のユーザー アカウントに対して一度にアクションを実行する

影響を受ける複数のユーザーに対して一度にアクションを実行するには:

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **ユーザー** > **リスクの高いユーザー**] を選択します。

2. [ **危険なユーザー** ] タブで、アクションを実行するユーザーのセットを選択します。

3. 実行するアクションを次のいずれかを選択します。

    - パスワードのリセット

    - サインインをブロックする

    - 侵害されたユーザーを確認する

    - ユーザー リスクを無視する

> [!NOTE]
> 管理している組織にAzure AD Premium P2ライセンスがある場合は、ユーザー リスクベースの条件付きアクセス ポリシーを有効にすることをお勧めします。 詳細については、「 [条件付きアクセス: ユーザー リスクベースの条件付きアクセス](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk-user)」を参照してください。

## <a name="related-content"></a>関連コンテンツ
[チュートリアル: ユーザー サインインのリスク検出を使用して Azure AD Multi-Factor Authentication またはパスワードの変更をトリガーする](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) (記事)\
[リスクとは何ですか?](/azure/active-directory/identity-protection/concept-identity-protection-risks) (記事) \
[リスクを修復し、ユーザーのブロックを解除する](/azure/active-directory/identity-protection/howto-identity-protection-remediate-unblock) (記事)