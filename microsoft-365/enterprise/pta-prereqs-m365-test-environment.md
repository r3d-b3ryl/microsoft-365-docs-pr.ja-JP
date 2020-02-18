---
title: Microsoft 365 テスト環境のパススルー認証に必要な ID およびデバイス アクセスの前提条件
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: パススルー認証用の前提条件で ID とデバイスのアクセスをテストするための Microsoft 365 環境を作成します。
ms.openlocfilehash: f9f5fd8f235787512d59b29dc06b080bc9cfa0ff
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085606"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境のパススルー認証に必要な ID およびデバイス アクセスの前提条件

*このテストラボ ガイドは、Microsoft 365 Enterprise テスト環境にのみ使用できます。*

[ID とデバイスのアクセス構成](microsoft-365-policies-configurations.md)は、構成と条件付きアクセス ポリシーのセットで、Office 365 および Microsoft 365 Enterprise の Enterprise Mobility + Security (EMS) などを含めた、Azure Active Directory (Azure AD) と統合されているすべてのサービスへのアクセスを保護します。

この記事では、ID とデバイス アクセス用の[パススルー認証の前提条件構成](identity-access-prerequisites.md#prerequisites)に関する要件を満たす Microsoft 365 テスト環境を構成する方法を説明します。

このテスト環境は、次に示す 8 つのフェーズで設定します。

1.  パススルー認証を実装するシミュレーション エンタープライズ Microsoft 365 テスト環境を構築する
2.  Azure AD シームレス シングル サインオンを構成する
3.  名前付きの場所を構成する
4.  パスワード ライトバックを構成する
5.  セルフサービスのパスワードのリセットを構成する
6.  多要素認証を構成する
7.  Azure AD Identity Protection を有効化する
8.  Exchange Online および Skype for Business Online に対して先進認証を有効化する

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a>フェーズ 1: パススルー認証を実装するシミュレーション エンタープライズ Microsoft 365 テスト環境を構築する

「[パススルー認証](pass-through-auth-m365-ent-test-environment.md)」の手順に従います。

最終的な構成は、次のようになります。

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>フェーズ 2: Azure AD シームレス シングル サインオンを構成する

[テスト ラボ ガイドの「Azure AD シームレス シングル サインオン」のフェーズ 2](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) に説明されている手順に従います。

## <a name="phase-3-configure-named-locations"></a>フェーズ 3: 名前付きの場所を構成する

最初に、組織で使用されているパブリック IP アドレスまたはアドレス範囲を確認します。

次に、「[Azure Active Directory で名前付きの場所を構成する](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)」の手順に従って、アドレスまたはアドレス範囲を名前付きの場所として追加します。 

## <a name="phase-4-configure-password-writeback"></a>フェーズ 4: パスワード ライトバックを構成する

[テスト ラボ ガイドの「パスワード ライトバック」のフェーズ 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) に説明されている手順に従います。

## <a name="phase-5-configure-self-service-password-reset"></a>フェーズ 5: セルフサービスのパスワードのリセットを構成する

次に、テスト ラボ ガイドの[「パスワードのリセット」のフェーズ 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) に説明されている手順に従います。 

特定の Azure AD グループに含まれるアカウントのパスワード リセットを有効にする場合は、それらのアカウントを**パスワードのリセット** グループに追加します。

- ユーザー 2
- ユーザー 3
- ユーザー 4
- ユーザー 5

User 2 アカウントのパスワードのリセットのみテストします。

## <a name="phase-6-configure-multi-factor-authentication"></a>フェーズ 6: 多要素認証を構成する

次のユーザー アカウントについて、[テスト ラボ ガイドの「多要素認証」のフェーズ 2](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) に説明されている手順に従います。

- ユーザー 2
- ユーザー 3
- ユーザー 4
- ユーザー 5

User 2 アカウントの多要素認証のみテストします。

## <a name="phase-7-enable-azure-ad-identity-protection"></a>フェーズ 7: Azure AD Identity Protection を有効化する

[テスト ラボ ガイドの「Azure AD Identity Protection」のフェーズ 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) に説明されている手順に従います。 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>フェーズ 8: Exchange Online および Skype for Business Online に対して先進認証を有効化する

Exchange Online については、[こちら](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)で説明されている手順に従います。 

Skype for Business Online については、

1. [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) に接続します。

2. 次のコマンドを実行します。

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. 次のコマンドを使用して、変更が成功したことを確認します。

  ```powershell
  Get-CsOAuthConfiguration
  ```

上述の手順により、ID とデバイス アクセス用の[パススルー認証の前提条件構成](identity-access-prerequisites.md#prerequisites)に関する要件を満たすテスト環境が作成されます。 

## <a name="next-step"></a>次の手順

[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)を使用して、前提条件に基づいて構築し ID とデバイスを保護するポリシーを構成します。

## <a name="see-also"></a>関連項目

[その他の ID のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md#identity)

[フェーズ 2: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)

