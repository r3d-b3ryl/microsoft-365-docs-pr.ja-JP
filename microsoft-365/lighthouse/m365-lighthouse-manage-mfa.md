---
title: 多要素認証の管理
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
description: 管理サービス プロバイダー (MSP) が Microsoft 365 Lighthouse、多要素認証を管理する方法について説明します。
ms.openlocfilehash: 4587dffbe45eacaf62c49d0c84aeef86455980e1
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557282"
---
# <a name="manage-multifactor-authentication"></a>多要素認証の管理

> [!NOTE]
> この記事で説明する機能はプレビューで、変更される可能性があります。要件を満たすパートナーだけが [利用できます](m365-lighthouse-requirements.md)。 組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。

Azure Active Directory (Azure AD) 多要素認証 (MFA) は、データとアプリケーションへのアクセスを保護し、2 番目の形式の認証を使用して別のセキュリティ層を提供します。 [多要素認証] タブには、テナント全体の MFA 有効化の状態に関する詳細情報が表示されます。 一覧で任意のテナントを選択すると、MFA を必要とする条件付きアクセス ポリシーが既に構成されている場合や、MFA にまだ登録していないユーザーなど、そのテナントの詳細が表示されます。

中小規模のビジネス (SMB) のお客様向けには、少なくともセキュリティの既定値 [を有効に](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) してください。 より複雑なシナリオでは、条件付きアクセス [を使用して](/azure/active-directory/conditional-access/overview) 特定のポリシーを構成できます。

## <a name="before-you-begin"></a>はじめに

テナントがリストに表示される前に、次の条件を満たしている必要があります。

- 顧客テナントには、各ユーザー Azure AD Premiumライセンスが必要です。 MFA をサポートするライセンスの詳細については、「多要素認証の機能と[ライセンスAzure AD」を参照してください](/azure/active-directory/authentication/concept-mfa-licensing)。

- 顧客テナントは、テナント内でアクティブMicrosoft 365 Lighthouse。 テナントがアクティブかどうかを確認する方法については、「テナントリスト[Microsoft 365 Lighthouseを参照してください](/microsoft-365/lighthouse/m365-lighthouse-tenant-list-overview)。

## <a name="enable-mfa-for-a-tenant"></a>テナントの MFA を有効にする

1. ライトハウスの左側のナビゲーション ウィンドウで、[ユーザー] を **選択します**。

2. [多 **要素認証] タブを** 選択します。

3. テナントの一覧からテナントを選択し、詳細ウィンドウを開きます。

4. [MFA 有効化 **] タブの** [セキュリティの既定値 **を持つ MFA] で、[** セキュリティの既定値を有効 **にする] を選択します**。

5. **[変更の保存]** を選択します。

条件付きアクセスを使用して MFA を有効にするには、「チュートリアル: 多要素認証を使用してユーザー サインイン イベントAzure AD[セキュリティで保護する」を参照してください](/azure/active-directory/authentication/tutorial-enable-azure-mfa)。

## <a name="notify-users-who-arent-registered-for-mfa"></a>MFA に登録されていないユーザーに通知する

1. ライトハウスの左側のウィンドウで、[ユーザー] を **選択します**。

2. [多 **要素認証] タブを** 選択します。

3. テナントの一覧からテナントを選択し、詳細ウィンドウを開きます。

4. [MFA に **登録されていないユーザー** ] タブで、通知するユーザーを選択します。

5. [メール **の作成] を選択します**。

ライトハウスは、既定のメール クライアントを開き、MFA に登録する手順が記載された電子メール メッセージを事前設定します。 選択したユーザーはすべて BCC 行に含まれます。 ユーザーを個別に電子メールで送信する場合は、ユーザー名の横にあるメール アイコンを選択できます。

別のメール アカウントを使用する場合は、ユーザーの一覧をファイルにエクスポートできます。 また、会社のブランド化でカスタマイズできるサンプルメール テンプレートをダウンロードすることもできます。

## <a name="next-steps"></a>次の手順

MFA が有効になると、セルフサービス パスワードのリセットAzure Active Directory (Azure AD) を有効にできます。 この機能を使用すると、管理者やヘルプ デスクに関与する必要なく、ユーザーはパスワードを変更またはリセットできます。 詳細については、「Manage [self-service password reset」を参照してください](m365-lighthouse-manage-sspr.md)。

## <a name="related-content"></a>関連コンテンツ

[複数要素認証Azure Active Directory展開を計画](/azure/active-directory/authentication/howto-mfa-getstarted)する (記事)\
[セキュリティの既定値は何ですか?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) (記事)\
[条件付きアクセスとは](/azure/active-directory/conditional-access/overview) (記事)\
[ユーザーごとの MFA から条件付きアクセスにユーザー](/azure/active-directory/authentication/howto-mfa-getstarted#convert-users-from-per-user-mfa-to-conditional-access-based-mfa) を変換する方法について説明します (記事)
