---
title: '手順 3: ユーザーのサインインをセキュリティで保護して管理する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: ユーザーの Windows デバイスへのサインインと、Microsoft 365 へのサインインのセキュリティ強化を行うことができます。
ms.openlocfilehash: 6f45d61694cabd10587ff13bd787fa42bdaeac01
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370194"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a>手順 3: ユーザーのサインインをセキュリティで保護して管理する

![フェーズ 2 - ID](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a>Windows Hello for Business を使用する

*この手順は省略可能であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

Windows 10 Enterprise の Windows Hello for Business では、Windows デバイスにサインオンするときのパスワードを強力な 2 要素認証に置き換えます。 この 2 要素認証は、デバイスと生体認証または PIN に関連付けられる新しい種類のユーザー資格情報です。

詳しくは、「[Windows Hello for Business の概要](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)」をご覧ください。


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a>Azure Multi-Factor Authentication の設定

*この手順は省略可能であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

この手順では、ユーザーのサインインとトランザクションに Azure Multi-Factor Authenticatio (MFA) を設定して、セキュリティの第 2 の層を追加します。 MFA により、ユーザーがパスワードを正しく入力した後に、追加の認証方法が求められます。 MFA を使わない場合、パスワードが唯一の認証方法になります。 パスワードの問題点は、多くのパスワードが攻撃者が簡単に推測できるものであること、また知らない間に信頼できない人物に共有されてしまうことがあるという点です。

MFA での 2 番目のセキュリティ層には次のものがあります。

- 容易になりすましたり複製することができない信頼性のあるパーソナル デバイス (スマートフォンなど)。
- 指紋認証などの生体認証属性。

ユーザーは、[条件付きアクセス ポリシー](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)で MFA を有効にして、第 2 の認証方法を構成することができます。これにより、Azure Active Directory (Azure AD) グループを使用して、パイロット ユーザー、地理的地域、部門などのユーザーの指定されたセットに MFA を展開できるようになります。 MFA が有効になっていることをユーザーに知らせ、その要件 (サインインにスマートフォンを使用することを義務付けるなど) をユーザーが理解し、正常にログインできることを確認します。 

詳細については、「[クラウドベースの Azure Multi-Factor Authentication の計画](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)」を参照してください。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: Azure Multi-Factor Authentication](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-mfa)を確認できます。

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>資格情報が侵害されないように保護する

*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*

このセクションでは、資格情報が侵害されないように保護するポリシーを構成する方法を学習します。攻撃者は組織のクラウド サービスとデータにアクセスするため、ユーザーのアカウント名とパスワードを突き止めて、資格情報を侵害しようとします。 Azure AD Identity Protection は、攻撃者によるユーザー アカウントの資格情報の侵害を防ぐさまざまな方法を提供します。

Azure AD Identity Protection では次の作業を実行できます。

|||
|:---------|:---------|
|組織の ID における潜在的な脆弱性の洗い出しと対処|Azure AD では機械学習を使用して、サインインやサインイン後のアクティビティなどの異常や不審なアクティビティを検出します。 このデータを使用して、Azure AD Identity Protection でレポートとアラートを生成すると、ユーザーによる問題の評価と措置に役立ちます。|
|組織の ID に関連する不審なアクションの検出と自動対応|特定のリスク レベルに到達すると自動的に検出された問題に対処するよう、リスクベースのポリシーを構成できます。 Azure AD および Microsoft Intune で提供されている他の条件付きアクセス コントロールにこれらのポリシーが加わると、その次のサインイン用のパスワードのリセットや Azure Multi-Factor Authentication を含め、自動的にアクセスをブロックしたり、修正処置を取ったりすることができます。|
|不審なインシデントを調査し、管理操作によって解決する|セキュリティ インシデントに関する情報を使用して、リスク イベントを調査できます。調査の追跡と修復処理 (パスワードのリセットなど) の開始のための基本的なワークフローを利用できます。|

[Azure AD Identity Protection の詳細情報](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)を参照してください。

[Azure AD Identity Protection を有効にする手順](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)を参照してください。

この手順の結果として、Azure AD Identity Protection が有効になり、次の目的で Azure AD Identity Protection を使用できるようになります。

- 潜在的な ID の脆弱性に対処する。
- 資格情報の侵害の疑いがあるものを検出する。
- 発生している不審な ID インシデントを調査して対処する。

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-ident-prot)を確認できます。

|||
|:-------|:-----|
|![手順 4](./media/stepnumbers/Step4.png)| [ユーザー アカウントを追加する](identity-add-user-accounts.md) |
