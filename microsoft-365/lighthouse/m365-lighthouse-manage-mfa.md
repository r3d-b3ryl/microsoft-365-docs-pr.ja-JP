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
description: Microsoft 365 Lighthouse を使用するマネージド サービス プロバイダー (MSP) 向けに、多要素認証を管理する方法を説明します。
ms.openlocfilehash: 4587dffbe45eacaf62c49d0c84aeef86455980e1
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557282"
---
# <a name="manage-multifactor-authentication"></a>多要素認証の管理

> [!NOTE]
> この記事で説明する機能はプレビュー段階であり、変更される可能性があり、[要件](m365-lighthouse-requirements.md)を満たすパートナーのみが利用できます。 組織に Microsoft 365 Lighthouse がない場合は、「[Microsoft 365 Lighthouse にサインアップする](m365-lighthouse-sign-up.md)」を参照してください。

Azure Active Directory (Azure AD) 多要素認証 (MFA) は、データとアプリケーションへのアクセスを保護するのに役立ち、2 つ目の形式の認証を使用して別のセキュリティ層を提供します。 [多要素認証] タブには、テナント全体での MFA 有効化の状態に関する詳細情報が表示されます。 一覧から任意のテナントを選択すると、そのテナントの詳細が表示されます。これには、MFA を必要とする条件付きアクセス ポリシーが既に構成されているものと、MFA にまだ登録していないユーザーが含まれます。

中小企業 (SMB) のお客様の場合は、少なくとも[セキュリティの既定値群](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)を有効にすることをお勧めします。 より複雑なシナリオでは、[条件付きアクセス](/azure/active-directory/conditional-access/overview)を使用して特定のポリシーを構成できます。

## <a name="before-you-begin"></a>始める前に

テナントがリストに表示される前に、次の条件を満たす必要があります:

- 顧客テナントには、ユーザーごとに Azure AD Premium ライセンスが必要です。 MFA をサポートするライセンスの詳細については、「[Azure AD 多要素認証の機能とライセンス](/azure/active-directory/authentication/concept-mfa-licensing)」を参照してください。

- 顧客テナントは Microsoft 365 Lighthouse 内でアクティブである必要があります。 テナントがアクティブかどうかを確認する方法については「[Microsoft 365 Lighthouse テナント リストの概要](/microsoft-365/lighthouse/m365-lighthouse-tenant-list-overview)」を参照してください。

## <a name="enable-mfa-for-a-tenant"></a>テナントの MFA を有効にする

1. Lighthouse の左側のナビゲーション ウィンドウで、**[ユーザー]** を選択します。

2. **[多要素認証]** タブを選択します。

3. テナントの一覧からテナントを選択し、詳細ウィンドウを開きます。

4. **[MFA 有効化]** タブで、 **[セキュリティの既定値群を伴う MFA]** で、**[セキュリティの既定値群の有効化]** を選択します。

5. **[変更の保存]** を選択します。

条件付きアクセスを使用して MFA を有効にするには、「[チュートリアル: Azure AD 多要素認証を使用してユーザー サインイン イベントをセキュリティで保護する](/azure/active-directory/authentication/tutorial-enable-azure-mfa)」を参照してください。

## <a name="notify-users-who-arent-registered-for-mfa"></a>MFA に登録されていないユーザーに通知する

1. Lighthouse の左側のウィンドウで、**[ユーザー]** を選択します。

2. **[多要素認証]** タブを選択します。

3. テナントの一覧からテナントを選択し、詳細ウィンドウを開きます。

4. **[MFA に登録していないユーザー]** タブで、通知するユーザーを選択します。

5. **[メールの作成]** を選択します。

Lighthouse によって既定のメール クライアントが開き、MFA に登録する手順がメール メッセージに事前入力されます。 選択したすべてのユーザーが BCC 行に含まれます。 ユーザーに個別にメールを送信する場合は、ユーザー名の横にあるメール アイコンを選択できます。

別のメール アカウントを使用する場合は、ユーザーのリストをファイルにエクスポートできます。 会社のブランドでカスタマイズできるサンプル メール テンプレートをダウンロードすることもできます。

## <a name="next-steps"></a>次の手順

MFA が有効になったら、Azure Active Directory (Azure AD) のセルフサービス パスワード リセットを有効にすることができます。 この機能を使用すると、管理者やヘルプ デスクの関与なしにパスワードを変更またはリセットできます。 詳細については、「[セルフサービスでパスワード リセットを管理する](m365-lighthouse-manage-sspr.md)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[Azure Active Directory 多要素認証展開の計画](/azure/active-directory/authentication/howto-mfa-getstarted) (記事)\
[セキュリティの既定値群とは?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) (記事)\
[条件付きアクセスとは](/azure/active-directory/conditional-access/overview) (記事)\
[ユーザーごとの MFA から条件付きアクセスにユーザーを変換する方法の説明](/azure/active-directory/authentication/howto-mfa-getstarted#convert-users-from-per-user-mfa-to-conditional-access-based-mfa) (記事)
