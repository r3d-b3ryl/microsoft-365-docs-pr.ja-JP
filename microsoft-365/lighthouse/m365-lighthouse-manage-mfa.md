---
title: Microsoft 365 Lighthouseで多要素認証を管理する
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
description: Microsoft 365 Lighthouse を使用するマネージド サービス プロバイダー (MSP) 向けに、多要素認証を管理する方法を説明します。
ms.openlocfilehash: 79690fb052c611fd9d89cf0cdbde8fc8b3f37832
ms.sourcegitcommit: 2aa5c026cc06ed39a9c1c2bcabd1f563bf5a1859
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695640"
---
# <a name="manage-multifactor-authentication-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseで多要素認証を管理する

Azure Active Directory (Azure AD) 多要素認証 (MFA) は、データとアプリケーションへのアクセスを保護するのに役立ち、2 つ目の形式の認証を使用して別のセキュリティ層を提供します。 [多要素認証] タブには、テナント全体での MFA 有効化の状態に関する詳細情報が表示されます。 一覧から任意のテナントを選択すると、MFA を必要とする条件付きアクセス ポリシーが既に構成されていることや、MFA にまだ登録していないユーザーなど、そのテナントの詳細が表示されます。

中小企業 (SMB) のお客様の場合は、少なくとも[セキュリティの既定値群](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)を有効にすることをお勧めします。 より複雑なシナリオでは、[条件付きアクセス](/azure/active-directory/conditional-access/overview)を使用して特定のポリシーを構成できます。

## <a name="before-you-begin"></a>始める前に

テナントがリストに表示される前に、次の条件を満たす必要があります:

- 顧客テナントには、ユーザーごとに Azure AD Premium ライセンスが必要です。 MFA をサポートするライセンスの詳細については、「[Azure AD 多要素認証の機能とライセンス](/azure/active-directory/authentication/concept-mfa-licensing)」を参照してください。

- 顧客テナントは Microsoft 365 Lighthouse 内でアクティブである必要があります。 テナントがアクティブかどうかを確認する方法については「[Microsoft 365 Lighthouse テナント リストの概要](/microsoft-365/lighthouse/m365-lighthouse-tenant-list-overview)」を参照してください。

## <a name="enable-mfa-for-a-tenant"></a>テナントの MFA を有効にする

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **ユーザー** > **多要素認証**] を選択します。

2. [ **多要素認証** ] タブで、MFA を使用していないテナントを探し、そのテナントを選択してテナントの詳細ウィンドウを開きます。

3. **[MFA 有効化]** タブで、 **[セキュリティの既定値群を伴う MFA]** で、**[セキュリティの既定値群の有効化]** を選択します。

4. **[変更の保存]** を選択します。

条件付きアクセスを使用して MFA を有効にするには、「[チュートリアル: Azure AD 多要素認証を使用してユーザー サインイン イベントをセキュリティで保護する](/azure/active-directory/authentication/tutorial-enable-azure-mfa)」を参照してください。

## <a name="notify-users-who-arent-registered-for-mfa"></a>MFA に登録されていないユーザーに通知する

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **ユーザー** > **多要素認証**] を選択します。

2. [ **多要素認証** ] タブで、MFA に登録されていないユーザーを持つテナントを探し、テナントを選択してテナントの詳細ウィンドウを開きます。

3. [ **MFA に登録されていないユーザー** ] タブを選択します。

4. MFA に登録する必要がある他のすべてのユーザーを一覧から選択し、[ **電子メールの作成**] を選択します。

> [!TIP]
> 一覧内のいずれかのユーザー アカウントが、MFA を必要としない緊急アクセス アカウントまたはサービス アカウントである場合は、それらのユーザー アカウントを選択し、[ **ユーザーの除外**] を選択します。 除外されたユーザー アカウントは、MFA に登録されていないユーザーの一覧に表示されなくなります。

> [!NOTE]
> MFA に登録されていないユーザーの一覧に共有メールボックス アカウントまたは非アクティブなユーザー アカウントが表示される場合は、それらのアカウントのサインインをブロックして、この一覧に表示されないようにすることをお勧めします。


Lighthouse によって既定のメール クライアントが開き、MFA に登録する手順がメール メッセージに事前入力されます。 選択したすべてのユーザーが BCC 行に含まれます。 ユーザーに個別にメールを送信する場合は、ユーザー名の横にあるメール アイコンを選択できます。

別のメール アカウントを使用する場合は、ユーザーのリストをファイルにエクスポートできます。 会社のブランドでカスタマイズできるサンプル メール テンプレートをダウンロードすることもできます。

## <a name="next-steps"></a>次の手順

MFA が有効になったら、Azure Active Directory (Azure AD) のセルフサービス パスワード リセットを有効にすることができます。 この機能を使用すると、管理者やヘルプ デスクの関与なしにパスワードを変更またはリセットできます。 詳細については、「[Microsoft 365 Lighthouseでのセルフサービス パスワード リセットの管理](m365-lighthouse-manage-sspr.md)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[Azure Active Directory 多要素認証展開の計画](/azure/active-directory/authentication/howto-mfa-getstarted) (記事)\
[セキュリティの既定値群とは?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) (記事)\
[条件付きアクセスとは](/azure/active-directory/conditional-access/overview) (記事)\
[ユーザーごとの MFA から条件付きアクセスにユーザーを変換する方法の説明](/azure/active-directory/authentication/howto-mfa-getstarted#convert-users-from-per-user-mfa-to-conditional-access-based-mfa) (記事)
