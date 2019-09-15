---
title: '手順 4: セキュリティで保護されたユーザー認証を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: ユーザー アカウントの多要素認証について理解し、構成します。
ms.openlocfilehash: 2a4a0926a08ae8279523219a2d7a2386ea0c6742
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981848"
---
# <a name="step-4-configure-secure-user-authentication"></a>手順 4: セキュリティで保護されたユーザー認証を構成する

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a>多要素認証をセットアップする

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

この手順では、ユーザー サインインとトランザクションに 2 番目のセキュリティ層を追加するため、多要素認証 (MFA) をセットアップします。MFA では、ユーザーがパスワードを正しく入力した後に別の検証方式が必要になります。MFA を使用しない場合、パスワードが唯一の検証方式となります。パスワードの問題点は、多くのパスワードが攻撃者が簡単に推測できるものであることと、また知らない間に信頼できない人物と共有してしまうことがあるという点です。

MFA での 2 番目のセキュリティ層には次のものがあります。

- 容易になりすましたり複製することができない信頼性のあるパーソナル デバイス (スマートフォンなど)。
- 指紋認証などの生体認証属性。

ユーザーは、[条件付きアクセス ポリシー](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)で MFA を有効にして、第 2 の認証方法を構成することができます。これにより、Azure Active Directory (Azure AD) グループを使用して、パイロット ユーザー、地理的地域、部門などのユーザーの指定されたセットに MFA を展開できるようになります。 MFA が有効になっていることをユーザーに知らせ、その要件 (サインインにスマートフォンを使用することを義務付けるなど) をユーザーが理解し、正常にログインできることを確認します。 

詳細については、[多要素認証の計画](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)を参照してください。

>[!Note]
>Microsoft Office 2010 以前や Apple Mail などの一部のアプリケーションでは MFA を使用できません。このようなアプリを使用するには、従来のパスワードの代わりに「アプリ パスワード」を使用する必要があります。アプリ パスワードでは、アプリが MFA をバイパスして処理を続行できます。アプリ パスワードについては、「[Office 365 のアプリ パスワードを作成する](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)」を参照してください。
>

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: 多要素認証](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-mfa)を確認できます。

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>脆弱なパスワードを防止する

*この手順は省略可能であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

ユーザーが容易に決定されたパスワードを作成するのを防ぐには、Azure AD のパスワード保護を使用します。その機能では、指定のグローバル禁止パスワード リストとカスタムの禁止パスワード リスト (省略可能) を使用します。 たとえば、次のような組織固有の用語を指定できます。

- ブランド名
- 製品名
- 場所 (たとえば、会社の本部など)
- 会社固有の内部用語
- 会社固有の意味を持つ略語。

[クラウド内](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)および[オンプレミスの Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)に対する脆弱なパスワードを禁止できます。

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-password-prot)を確認できます。

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>資格情報が侵害されないように保護する

*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*

このセクションでは、資格情報が侵害されないように保護するポリシーを構成する方法を学習します。攻撃者は組織のクラウド サービスとデータにアクセスするため、ユーザーのアカウント名とパスワードを突き止めて、資格情報を侵害しようとします。 Azure AD Identity Protection は、攻撃者が複数のアカウントやグループを横方向に移動し、最終的に最も重要なデータにたどり着くのを防ぐさまざまな方法を提供します。

Azure AD Identity Protection では次の作業を実行できます。

|||
|:---------|:---------|
|組織の ID における潜在的な脆弱性の洗い出しと対処|Azure AD では機械学習を使用して、サインインやサインイン後のアクティビティなどの異常や不審なアクティビティを検出します。 このデータを使用して、Azure AD Identity Protection でレポートとアラートを生成すると、ユーザーによる問題の評価と措置に役立ちます。|
|組織の ID に関連する不審なアクションの検出と自動対応|特定のリスク レベルに到達すると自動的に検出された問題に対処するよう、リスク ベースのポリシーを構成できます。 Azure AD および Microsoft Intune で提供されている他の条件付きアクセス コントロールにこれらのポリシーが加わると、その次のサインイン用のパスワードのリセットや多要素認証要求を含め、自動的にアクセスをブロックしたり、修正処置を取ったりすることができます。|
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

## <a name="monitor-tenant-and-sign-in-activity"></a>テナントとサインイン アクティビティを監視する

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

この手順では、Azure AD のレポートを使用して監査ログおよびサインイン アクティビティを確認します。2 種類のレポートを利用できます。

**監査ログ アクティビティ レポート**には、Azure AD テナントで実行されたすべてのタスクの履歴が記録されます。このレポートから、次のような情報を確認できます。

- 管理者グループにユーザーを追加したユーザー
- 特定のアプリにサインインしたユーザー
- パスワード リセットの実行回数

**サインイン アクティビティ レポート**には、監査ログ レポートで報告されたタスクを実行したユーザーが記録されます。このレポートから、次のような情報を確認できます。

- 調査中の特定のユーザーのサインイン パターン
- 日、週、月あたりのサインインの回数
- 失敗したサインインの回数とそのアカウント

レポートとレポートへのアクセス方法の詳細については、「[Azure Active Directory レポート](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)」を参照してください。

この手順を実行すると、これらのレポートを認識でき、また計画とセキュリティの目的でレポートを使用して Azure AD のイベントとアクティビティに関する情報を把握する方法を理解できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [ユーザーのアクセスを簡素化する](identity-password-reset.md) |

