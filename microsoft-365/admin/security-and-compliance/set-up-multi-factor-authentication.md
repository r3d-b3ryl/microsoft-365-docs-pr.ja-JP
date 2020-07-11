---
title: ユーザーの多要素認証を設定する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 組織向けに多要素認証を設定する方法について説明します。
monikerRange: o365-worldwide
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083540"
---
# <a name="set-up-multi-factor-authentication"></a>多要素認証をセットアップする
  
[多要素認証 (MFA) を理解し、Microsoft 365でサポートされていること](multi-factor-authentication-microsoft-365.md) を理解したら、それを設定し、組織にロールアウトします。

作業を開始する前に、これらの特殊条件が適用されているかどうかを確認し、適切なアクションを行います。

- Windows デバイスで Office 2013 クライアントを使用している場合は、[最新のライセンス認証を有効化](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication) します。

- Active Directory フェデレーション サービス (AD FS) を使用しているサードパーティ ディレクトリ サービスがある場合は、Azure MFA サーバーをセットアップします。 詳細については、「[Azure Multi-factor Authentication およびサードパーティ製の VPN ソリューションでの高度なシナリオ](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)」 を参照してください。

他のすべてのユーザーは、必要に応じて追加認証を求められます。 詳細については、「[2要素検証方法と設定](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device)」 を参照してください。

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>手順1: ユーザーに MFA の使用を要求する方法を決定する

> [!NOTE]
> MFA を設定または変更するには、グローバル管理者である必要があります。 ユーザーがサインインのために MFA を使用するには、3つの方法があります。詳細については、「[Microsoft 365 の MFA サポート](multi-factor-authentication-microsoft-365.md)」 を参照してください。

- セキュリティの既定値 (中小企業に推奨)

  2019年10月21日以降にサブスクリプションまたは試用版を購入した場合に、MFA を要求するメッセージが予期せず表示されます。 [セキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) の設定は、サブスクリプションに対して自動的に有効になります。
  
  新しい Microsoft 365 サブスクリプションでは、すべてにおいて自動的にセキュリティの既定値が有効になります。 つまり、すべてのユーザーが MFA を設定し、モバイル デバイスに Microsoft Authenticator アプリをインストールする必要があります。

  すべてのユーザーは、追加の検証方法として Microsoft Authenticator アプリを使用する必要があります。また、従来の認証がブロックされます。 

- 条件付きアクセス ポリシー (大企業に推奨)

  ユーザーは、MFA の登録中に追加の検証方法を選択します。

- ユーザー アカウント単位 (推奨されません)

  ユーザーは、MFA の登録中に追加の検証方法を選択します。

## <a name="step-2-test-mfa-on-your-pilot-users"></a>手順 2. パイロット ユーザーに MFA をテストする

条件付きアクセス ポリシーまたはユーザー単位の MFA を使用している場合 (推奨されません)、MFA の登録とサインインをテストするために、会社または組織のパイロット ユーザーを選択します。例えば：

- 条件付きアクセス ポリシーの場合、パイロット ユーザー グループを作成し、グループとすべてのアプリのメンバーに MFA を要求するポリシーを作成します。 次に、パイロット ユーザーのアカウントをグループに追加します。

- ユーザーごとの MFA については、パイロット ユーザーのユーザー アカウントの MFA を1つずつ有効にします。

パイロット ユーザーと協力して質問や問題に対処し、組織にスムーズに展開するための準備を行います。

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>手順 3. MFA の到来を組織に知らせる

従業員の理解を深めるために、メール通知、廊下ポスター、チーム会議、または公的な研修を活用します。

- サインインに MFA が必要な理由
- [追加の検証手法を登録する方法](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [登録後のサインインの方法](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [追加の検証手法を変更する方法](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [新しいスマートフォンのような状況に対処する方法](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

最も重要な点は、従業員を驚かせることなく、***MFA の要件がいつ課されるか*** について彼らが理解しているかどうかを確認することです。

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>手順 4. MFA 要件を組織またはユーザーに展開する

選択した MFA の要件に基づいて、パイロット テスター以外の従業員に MFA 認証を展開します。

### <a name="security-defaults"></a>セキュリティの既定値

Azure ポータル内の Azure Active Directory (Azure AD) の **プロパティ** ウィンドウで、セキュリティの既定値を有効または無効にします。

1.  グローバル管理者の資格情報を使用して、[MIcrosoft 365 管理センター](https://admin.microsoft.com) にサインインします。
2.  [[Azure Active Directory] のプロパティ ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) にアクセスします。
3.  ページの下部で、[**セキュリティの既定値の管理**] を選択します。
4.  セキュリティの規定値を有効にするには [**はい**] を選び、セキュリティの規定値を無効にするには [**いいえ**] を選んで [**保存**] を選択します。

[条件付きアクセスのベースライン ポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) を使用している場合は、次の手順に従ってセキュリティの既定値を使用します。

1.  [条件付きアクセス ポリシー ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) へ移動します。
2.  各ベースライン ポリシーで [**オン**] を選択し、 [**ポリシーを有効にする**] を [**オフ**] に設定します。
2.  [[Azure Active Directory] のプロパティ ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) にアクセスします。
4.  ページの下部で、[**セキュリティの既定値の管理**] を選択します。
5.  セキュリティの規定値を有効にするには [**はい**] を選び、セキュリティの規定値を無効にするには [**いいえ**] を選んで [**保存**] を選択します。

### <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

サインインに MFA が必要なユーザーのグループを含む適切なポリシーを作成し、構成して有効にします。

### <a name="per-user-mfa-not-recommended"></a>ユーザーごとの MFA (推奨されません)

展開に対応する MFA のユーザー アカウントを有効にします。

### <a name="supporting-your-employees"></a>従業員をサポートする

従業員が MFA を登録してサインインするときに、IT スペシャリスト、IT 部門、またはヘルプデスクが質問に回答して、問題にすばやく対処することができます。

[MFA サインインのトラブルシューティングに関する情報](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2) については、この記事を参照してください。 


