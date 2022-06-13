---
title: Microsoft 365 Lighthouseでセルフサービスパスワードリセットを管理する
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
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、セルフサービスのパスワード リセットを管理する方法について説明します。
ms.openlocfilehash: 0af624e93ae9321834e147f829a87f09c36dedf7
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66017678"
---
# <a name="manage-self-service-password-reset-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseでセルフサービスパスワードリセットを管理する

Microsoft 365 Lighthouseでは、パートナーはAzure Active Directory (Azure AD) のセルフサービス パスワード リセット (SSPR) を管理できます。 SSPR を使用すると、管理者やヘルプ デスクの関与なしでパスワードを変更またはリセットできます。 ユーザーのアカウントがロックされているか、パスワードを忘れた場合は、プロンプトに従ってブロックを解除し、職場に戻ることができます。 この機能により、ユーザーがデバイスまたはアプリケーションにサインインできない場合に、ヘルプ デスクの呼び出しと生産性の低下が軽減されます。

## <a name="before-you-begin"></a>始める前に

テナントがリストに表示される前に、次の条件を満たす必要があります:

- 顧客テナントには、ユーザーごとに Azure AD Premium ライセンスが必要です。 SSPR をサポートするライセンスの詳細については、「[Azure Active Directoryセルフサービス パスワード リセットのライセンス要件](/azure/active-directory/authentication/concept-sspr-licensing)」を参照してください。

- 顧客テナントは、Lighthouse 内でアクティブである必要があります。 テナントがアクティブかどうかを確認する方法については、[Microsoft 365 LighthouseのWindows 365 (クラウド PC) ページの概要に](m365-lighthouse-tenants-page-overview.md)関するページを参照してください。

## <a name="view-sspr-tenant-status"></a>SSPR テナントの状態を表示する

1. Lighthouse の左側のナビゲーション ウィンドウで、[ユーザー] を選択 **します**。

2. [ **パスワード リセット** ] タブを選択します。

[パスワード リセット] タブには、推奨設定を使用して SSPR を有効にしたテナントの概要、SSPR に登録していないユーザーの数、管理している組織全体での SSPR 展開の進行状況のテナント別の詳細な内訳が表示されます。

## <a name="enable-sspr-for-a-tenant"></a>テナントに対して SSPR を有効にする

1. Lighthouse の左側のナビゲーション ウィンドウで、**[ユーザー]** を選択します。

2. [ **パスワード リセット** ] タブを選択します。

3. テナントの一覧からテナントを選択し、詳細ウィンドウを開きます。

4. **Azure Active Directoryで [SSPR 設定の編集]** を選択して、Azure Active Directory (Azure AD) に移動します。

5. Azure AD で、すべてのユーザーまたは選択したユーザーに対して SSPR を有効にします。 詳細については、「[チュートリアル: ユーザーがセルフサービス パスワード リセットを使用してアカウントのロックを解除したり、パスワードをリセットしたりAzure Active Directoryできるようにする](/azure/active-directory/authentication/tutorial-enable-sspr)」を参照してください。

## <a name="notify-users-to-register-for-sspr"></a>SSPR に登録するようにユーザーに通知する

1. Lighthouse の左側のナビゲーション ウィンドウで、**[ユーザー]** を選択します。

2. [ **パスワード リセット** ] タブを選択します。

3. テナントの一覧からテナントを選択し、詳細ウィンドウを開きます。

4. 通知するユーザーを選択します。

5. **[メールの作成]** を選択します。

Lighthouse によって既定の電子メール クライアントが開き、SSPR に登録する手順が電子メール メッセージに事前設定されます。 選択したすべてのユーザーが BCC 行に含まれます。 ユーザーに個別にメールを送信する場合は、ユーザー名の横にあるメール アイコンを選択できます。

別のメール アカウントを使用する場合は、ユーザーのリストをファイルにエクスポートできます。 会社のブランドでカスタマイズできるサンプル メール テンプレートをダウンロードすることもできます。

## <a name="related-content"></a>関連コンテンツ

[Azure Active Directoryセルフサービスパスワード リセットの展開を計画する](/azure/active-directory/authentication/howto-sspr-deployment) (記事)\
[チュートリアル: ユーザーが自分のアカウントのロックを解除したり、Azure Active Directoryセルフサービスパスワード リセット (記事)\ を使用してパスワードをリセットしたりできるようにします](/azure/active-directory/authentication/tutorial-enable-sspr)。
[Azure AD で SSPR を有効にして構成する方法](https://www.youtube.com/watch?v=rA8TvhNcCvQ) (ビデオ)\
[Microsoft 365 Lighthouseで多要素認証を管理する](m365-lighthouse-manage-mfa.md) (記事)
