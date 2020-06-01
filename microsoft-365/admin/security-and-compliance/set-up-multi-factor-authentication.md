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
localization_priority: Normal
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
description: 組織で多要素認証をセットアップする方法について説明します。
monikerRange: o365-worldwide
ms.openlocfilehash: c84c66cc051363fbc582abfb5521f922440b6801
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432381"
---
# <a name="set-up-multi-factor-authentication"></a>多要素認証をセットアップする
  
[Microsoft 365 での多要素認証 (MFA) とそのサポート](multi-factor-authentication-microsoft-365.md)についての理解に基づいて、これを設定して組織にロールアウトします。

開始する前に、これらの特殊条件が適用されるかどうかを確認し、適切な操作を行います。

- Windows デバイス上に Office 2013 クライアントがある場合は、[先進認証を有効に](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)します。

- Active Directory フェデレーションサービス (AD FS) を備えたサードパーティ製のディレクトリサービスがある場合は、Azure MFA サーバーをセットアップします。 詳細については[、「Azure 多要素認証とサードパーティ製 VPN ソリューションを使用した高度なシナリオ](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)」を参照してください。

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>手順 1: ユーザーに MFA の使用を要求する方法を決定する

> [!NOTE]
> MFA を設定または変更するには、グローバル管理者である必要があります。 ユーザーがサインインに MFA を使用するよう要求するには、次の3つの方法があります。詳細については、「 [Microsoft 365 の MFA サポート](multi-factor-authentication-microsoft-365.md)」を参照してください。

- セキュリティの既定値 (小規模企業に推奨)

  2019年10月21日以降にサブスクリプションまたは試用版を購入した場合に、MFA を予期せずに要求されると、サブスクリプションに対して[セキュリティの既定値](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)が自動的に有効になります。
  
  すべての新しい Microsoft 365 サブスクリプションのセキュリティの既定値が自動的に有効になります。 これは、すべてのユーザーが MFA を設定し、モバイルデバイスに Microsoft Authenticator アプリをインストールする必要があることを意味します。

  すべてのユーザーは、追加の検証方法として Microsoft Authenticator アプリを使用する必要があり、従来の認証はブロックされます。 

- 条件付きアクセスポリシー (エンタープライズに推奨)

  ユーザーは、MFA 登録時に追加の確認方法を選択します。

- ユーザーごとのアカウント (推奨されません)

  ユーザーは、MFA 登録時に追加の確認方法を選択します。

## <a name="step-2-test-mfa-on-your-pilot-users"></a>手順 2.  パイロットユーザーの MFA をテストする

条件付きアクセスポリシーまたはユーザーごとの MFA (推奨されません) を使用している場合は、「ビジネスまたは組織のパイロットユーザー」を選択して、MFA の登録とサインインをテストします。例えば：

- 条件付きアクセスポリシーの場合は、パイロットユーザーグループと、グループのメンバーとすべてのアプリに対して MFA を必要とするポリシーを作成します。 次に、パイロットユーザーのアカウントをグループに追加します。

- ユーザー単位の MFA の場合は、パイロットユーザーのユーザーアカウントに対して MFA を1度ずつ有効にします。

パイロットユーザーと協力して、組織への円滑なロールアウトを準備するための質問や問題に対処します。

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>手順 3. MFA が届くことを組織に通知する

従業員が理解していることを確認するために、電子メール通知、hallway ポスター、チーム会議、または公式トレーニングを使用します。

- サインインに MFA が必要な理由
- [追加の確認方法を登録する方法](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [登録後のサインイン方法](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [その他の検証方法を変更する方法](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [新しいスマートフォンなどの状況を処理する方法](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

最も重要なのは、従業員が驚いていないように、 ***MFA 要件***を設定する時期を理解しておくことです。

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>手順 4. 組織またはユーザーに MFA 要件をロールアウトする

選択した MFA 要件の方法に基づいて、パイロットテスト担当者以外の従業員に MFA 認証をロールアウトします。

### <a name="security-defaults"></a>セキュリティの既定値

Azure portal で Azure Active Directory (Azure AD) の [**プロパティ**] ウィンドウを使用して、セキュリティの既定値を有効または無効にします。

1.  グローバル管理者の資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。
2.  [ [Azure Active Directory-プロパティ] ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)に移動します。
3.  ページの下部で、[**セキュリティの既定値の管理**] を選択します。
4.  [**はい]** を選択して**セキュリティの既定**値を有効にし、セキュリティの既定値を無効にして [**保存**] を選択します。

[基準条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)を使用している場合は、「セキュリティの既定値を使用して移動する方法」を参照してください。

1.  [[条件付きアクセスポリシー] ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)に移動します。
2.  有効になっているそれぞれ**の**ベースラインポリシーを選択し、[**ポリシーの有効化**] を [**オフ**] に設定します。
2.  [ [Azure Active Directory-プロパティ] ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)に移動します。
4.  ページの下部で、[**セキュリティの既定値の管理**] を選択します。
5.  [**はい]** を選択して**セキュリティの既定**値を有効にし、セキュリティの既定値を無効にして [**保存**] を選択します。

### <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

サインインのための MFA を必要とするユーザーのグループを含む適切なポリシーを作成、構成、および有効化します。

### <a name="per-user-mfa-not-recommended"></a>ユーザーごとの MFA (推奨しません)

ロールアウトに対応する MFA のユーザーアカウントを有効にします。

### <a name="supporting-your-employees"></a>従業員のサポート

従業員が MFA を登録してサインインを開始する際には、IT 専門家、IT 部門、またはヘルプデスクが質問に答えて、問題を迅速に解決できるようにしてください。

MFA のサインインの[トラブルシューティングに](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)ついては、この記事を参照してください。 


