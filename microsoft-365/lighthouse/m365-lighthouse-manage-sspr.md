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
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseパスワードのリセットを管理する方法について説明します。
ms.openlocfilehash: f9f8ef9a3c81281629c378fb4b55cd4c9a839c1d
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63311565"
---
# <a name="manage-self-service-password-reset"></a>セルフサービスパスワードのリセットを管理する

Microsoft 365 Lighthouseパートナーは、Azure Active Directory (Azure AD) セルフサービス パスワード リセット (SSPR) を管理できます。 SSPR を使用すると、管理者やヘルプ デスクに関与する必要なく、ユーザーはパスワードを変更またはリセットできます。 ユーザーのアカウントがロックされている場合、またはパスワードを忘れた場合は、プロンプトに従って自分自身のブロックを解除し、作業に戻る必要があります。 この機能により、ユーザーがデバイスやアプリケーションにサインインできない場合に、ヘルプ デスクの呼び出しや生産性の低下が軽減されます。

## <a name="before-you-begin"></a>始める前に

テナントがリストに表示される前に、次の条件を満たす必要があります:

- 顧客テナントには、ユーザーごとに Azure AD Premium ライセンスが必要です。 SSPR をサポートするライセンスの詳細については、「セルフサービス パスワードのリセットに関するライセンス要件[Azure Active Directoryを参照してください](/azure/active-directory/authentication/concept-sspr-licensing)。

- 顧客テナントは、ライトハウス内でアクティブである必要があります。 テナントがアクティブかどうかを確認する方法については、「テナントの概要」[Microsoft 365 Lighthouseを参照してください](m365-lighthouse-tenants-page-overview.md)。

## <a name="view-sspr-tenant-status"></a>SSPR テナントの状態を表示する

1. ライトハウスの左側のナビゲーション ウィンドウで、[ユーザー] を **選択します**。

2. [パスワードの **リセット] タブを選択** します。

[パスワードのリセット] タブには、推奨設定を使用して SSPR を有効にしたテナントの概要、SSPR に登録していないユーザーの数、および管理する組織全体での SSPR 展開の進行状況のテナント別の詳細な内訳が表示されます。

## <a name="enable-sspr-for-a-tenant"></a>テナントの SSPR を有効にする

1. Lighthouse の左側のナビゲーション ウィンドウで、**[ユーザー]** を選択します。

2. [パスワードの **リセット] タブを選択** します。

3. テナントの一覧からテナントを選択し、詳細ウィンドウを開きます。

4. [**SSPR 設定の編集] を選択してAzure Active Directory** に移動します (Azure Active Directory) Azure AD。

5. [Azure ADで、すべてのユーザーまたは選択したユーザーに対して SSPR を有効にしてください。 詳細については、「チュートリアル: ユーザーが自分のアカウントのロックを解除したり、セルフサービス パスワードのリセットを使用してパスワードをリセットAzure Active Directory[を有効にする」を参照してください](/azure/active-directory/authentication/tutorial-enable-sspr)。

## <a name="notify-users-to-register-for-sspr"></a>SSPR への登録をユーザーに通知する

1. Lighthouse の左側のナビゲーション ウィンドウで、**[ユーザー]** を選択します。

2. [パスワードの **リセット] タブを選択** します。

3. テナントの一覧からテナントを選択し、詳細ウィンドウを開きます。

4. 通知するユーザーを選択します。

5. **[メールの作成]** を選択します。

ライトハウスは既定の電子メール クライアントを開き、SSPR に登録する手順が記載された電子メール メッセージを事前設定します。 選択したすべてのユーザーが BCC 行に含まれます。 ユーザーに個別にメールを送信する場合は、ユーザー名の横にあるメール アイコンを選択できます。

別のメール アカウントを使用する場合は、ユーザーのリストをファイルにエクスポートできます。 会社のブランドでカスタマイズできるサンプル メール テンプレートをダウンロードすることもできます。

## <a name="related-content"></a>関連コンテンツ

[セルフサービス パスワードAzure Active Directory展開を](/azure/active-directory/authentication/howto-sspr-deployment)計画する (記事)\
[チュートリアル: セルフサービス パスワードのリセットを使用](/azure/active-directory/authentication/tutorial-enable-sspr)してユーザーがアカウントのロックを解除Azure Active Directoryパスワードをリセットする (記事)\
[SSPR を有効にして構成するAzure AD](https://www.youtube.com/watch?v=rA8TvhNcCvQ) (ビデオ)\
[多要素認証の管理](m365-lighthouse-manage-mfa.md) (記事)
