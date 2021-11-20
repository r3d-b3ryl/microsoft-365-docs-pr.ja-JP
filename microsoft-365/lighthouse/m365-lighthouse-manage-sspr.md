---
title: セルフサービスパスワードのリセットを管理する
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
description: 管理サービス プロバイダー (MSP) が Microsoft 365 Lighthouseを使用する場合は、セルフサービス パスワードのリセットを管理する方法について説明します。
ms.openlocfilehash: b8367d2ed2c088d56425b08c6da5dfd55fcd84b8
ms.sourcegitcommit: 2ea2105d40b60a87fc9aa30f392a73a3a9db6d99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2021
ms.locfileid: "61128606"
---
# <a name="manage-self-service-password-reset"></a>セルフサービスパスワードのリセットを管理する

> [!NOTE]
> この記事で説明する機能はプレビューで、変更される可能性があります。要件を満たすパートナーだけが [利用できます](m365-lighthouse-requirements.md)。 組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。

Microsoft 365 Lighthouseパートナーは、Azure Active Directory (Azure AD) セルフサービス パスワードリセット (SSPR) を管理できます。 SSPR を使用すると、管理者やヘルプ デスクに関与する必要なく、ユーザーはパスワードを変更またはリセットできます。 ユーザーのアカウントがロックされている場合、またはパスワードを忘れた場合は、プロンプトに従って自分自身のブロックを解除し、作業に戻る必要があります。 この機能により、ユーザーがデバイスやアプリケーションにサインインできない場合に、ヘルプ デスクの呼び出しや生産性の低下が軽減されます。

## <a name="before-you-begin"></a>はじめに

テナントがリストに表示される前に、次の条件を満たしている必要があります。

- 顧客テナントには、各ユーザー Azure AD Premiumライセンスが必要です。 SSPR をサポートするライセンスの詳細については、「セルフサービス パスワードのリセットに関するライセンス要件[Azure Active Directoryを参照してください](/azure/active-directory/authentication/concept-sspr-licensing)。

- 顧客テナントは、ライトハウス内でアクティブである必要があります。 テナントがアクティブかどうかを確認する方法については、「テナントの概要[」Microsoft 365 Lighthouseを参照してください](m365-lighthouse-tenants-page-overview.md)。

## <a name="view-sspr-tenant-status"></a>SSPR テナントの状態を表示する

1. ライトハウスの左側のナビゲーション ウィンドウで、[ユーザー] を **選択します**。

2. [パスワードの **リセット] タブを選択** します。

[パスワードのリセット] タブには、推奨設定を使用して SSPR を有効にしたテナントの概要、SSPR に登録していないユーザーの数、および管理する組織全体での SSPR 展開の進行状況のテナント別の詳細な内訳が表示されます。

## <a name="enable-sspr-for-a-tenant"></a>テナントの SSPR を有効にする

1. ライトハウスの左側のナビゲーション ウィンドウで、[ユーザー] を **選択します**。

2. [パスワードの **リセット] タブを選択** します。

3. テナントの一覧からテナントを選択し、詳細ウィンドウを開きます。

4. **[SSPR 設定の編集] を選択Azure Active Directory** (Azure Active Directory) に移動Azure AD。

5. [Azure ADで、すべてのユーザーまたは選択したユーザーに対して SSPR を有効にしてください。 詳細については、「チュートリアル: ユーザーが自分のアカウントのロックを解除したり、セルフサービス パスワードのリセットを使用してパスワードをリセットAzure Active Directory[を有効にする」を参照してください](/azure/active-directory/authentication/tutorial-enable-sspr)。

## <a name="notify-users-to-register-for-sspr"></a>SSPR への登録をユーザーに通知する

1. ライトハウスの左側のナビゲーション ウィンドウで、[ユーザー] を **選択します**。

2. [パスワードの **リセット] タブを選択** します。

3. テナントの一覧からテナントを選択し、詳細ウィンドウを開きます。

4. 通知するユーザーを選択します。

5. [メール **の作成] を選択します**。

ライトハウスは既定の電子メール クライアントを開き、SSPR に登録する手順が記載された電子メール メッセージを事前設定します。 選択したユーザーはすべて BCC 行に含まれます。 ユーザーを個別に電子メールで送信する場合は、ユーザー名の横にあるメール アイコンを選択できます。

別のメール アカウントを使用する場合は、ユーザーの一覧をファイルにエクスポートできます。 また、会社のブランド化でカスタマイズできるサンプルメール テンプレートをダウンロードすることもできます。

## <a name="related-content"></a>関連コンテンツ

[セルフサービス パスワードAzure Active Directory展開を](/azure/active-directory/authentication/howto-sspr-deployment)計画する (記事)\
[チュートリアル: セルフサービス パスワードのリセットを使用](/azure/active-directory/authentication/tutorial-enable-sspr)してユーザーがアカウントのロックを解除Azure Active Directoryパスワードをリセットする (記事)\
[SSPR を有効にして構成するAzure AD](https://www.youtube.com/watch?v=rA8TvhNcCvQ) (ビデオ)\
[多要素認証の管理](m365-lighthouse-manage-mfa.md) (記事)
