---
title: Microsoft 365 テスト環境のクラウド専用の ID およびデバイス アクセスの前提条件
author: kelleyvice-msft
f1.keywords:
  - NOCSH
ms.author: kvice
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
  - M365-subscription-management
  - Strat_O365_Enterprise
ms.custom: null
description: クラウド専用の認証用の前提条件で ID とデバイスのアクセスをテストするための Microsoft 365 環境を作成します。
---

# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境のクラウド専用の ID およびデバイス アクセスの前提条件

*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*

[ID およびデバイス アクセス](../security/office-365-security/microsoft-365-policies-configurations.md)構成は、Azure Active Directory (Azure AD) と統合されているすべてのサービスへのアクセスを保護するための、推奨される構成と条件付きアクセス ポリシーのセットです。

この記事では、ID とデバイス アクセス用の[クラウド専用の前提条件構成](../security/office-365-security/identity-access-prerequisites.md#prerequisites)に関する要件を満たす Microsoft 365 テスト環境を構成する方法を説明します。

このテスト環境は、次に示す 8 つのフェーズで設定します。

1. 軽量なテスト環境を構築する
2. 名前付きの場所を構成する
3. セルフサービスのパスワードのリセットを構成する
4. 多要素認証を構成する
5. ドメインに参加しているコンピューターのデバイスの自動登録Windowsする
6. パスワード保護Azure AD構成する 
7. Azure AD Identity Protection を有効化する
8. Exchange Online および Skype for Business Online に対して先進認証を有効化する

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>フェーズ 1: 軽量な Microsoft 365 テスト環境を構築する

「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」に説明されている手順に従います。
最終的な構成は、次のようになります。

![軽量な Microsoft 3656 Enterprise環境です。](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a>フェーズ 2: 名前付きの場所を構成する

最初に、組織で使用されているパブリック IP アドレスまたはアドレス範囲を確認します。

次に、「[Azure Active Directory で名前付きの場所を構成する](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)」の手順に従って、アドレスまたはアドレス範囲を名前付きの場所として追加します。 

## <a name="phase-3-configure-self-service-password-reset"></a>フェーズ 3: セルフサービス パスワードのリセットを構成する

次に、テスト ラボ ガイドの[「パスワードのリセット」のフェーズ 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) に説明されている手順に従います。 

特定の Azure AD グループに含まれるアカウントのパスワード リセットを有効にする場合は、それらのアカウントを **パスワードのリセット** グループに追加します。

- ユーザー 2
- ユーザー 3
- ユーザー 4
- ユーザー 5

User 2 アカウントのパスワードのリセットのみテストします。

## <a name="phase-4-configure-multi-factor-authentication"></a>フェーズ 4: 多要素認証を構成する

次のユーザー アカウントについて、[テスト ラボ ガイドの「多要素認証」のフェーズ 2](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) に説明されている手順に従います。

- ユーザー 2
- ユーザー 3
- ユーザー 4
- ユーザー 5

User 2 アカウントの多要素認証のみテストします。

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>フェーズ 5: ドメインに参加しているコンピューターのデバイスの自動登録Windowsする 

ドメイン[に参加しているコンピューターの](/azure/active-directory/devices/hybrid-azuread-join-plan)デバイスの自動登録を有効にするには、次のWindows従います。

## <a name="phase-6-configure-azure-ad-password-protection"></a>フェーズ 6: パスワード保護Azure AD構成する 

既知 [の脆弱なパスワードとその](/azure/active-directory/authentication/concept-password-ban-bad) バリアントをブロックするには、次の手順に従います。

## <a name="phase-7-enable-azure-ad-identity-protection"></a>フェーズ 7: Azure AD Identity Protection を有効化する

[テスト ラボ ガイドの「Azure AD Identity Protection」のフェーズ 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) に説明されている手順に従います。 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>フェーズ 8: Exchange Online および Skype for Business Online に対して先進認証を有効化する

Exchange Online については、[こちら](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)で説明されている手順に従います。 

Skype for Business Online については、

1. [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) に接続します。

2. 次のコマンドを実行します。

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. このコマンドを使用して、変更が成功したことを確認します。

  ```powershell
  Get-CsOAuthConfiguration
  ```

その結果、ID およびデバイス アクセスのクラウド専用前提条件構成の要件[](../security/office-365-security/identity-access-prerequisites.md#prerequisites)を満たすテスト環境が得られます。 

## <a name="next-step"></a>次の手順

[共通 ID とデバイスのアクセス ポリシー](../security/office-365-security/identity-access-policies.md)を使用して、前提条件に基づいて構築し ID とデバイスを保護するポリシーを構成します。

## <a name="see-also"></a>関連項目

[その他の ID のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md#identity)

[ID の展開](deploy-identity-solution-overview.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)
