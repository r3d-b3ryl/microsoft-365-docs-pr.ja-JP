---
title: '手順 4: セキュリティで保護されたユーザー認証を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: ユーザー アカウントの多要素認証について理解し、構成します。
ms.openlocfilehash: 73e884802329765fd6a89cfb7d0e04116c17968c
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072087"
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

MFA を有効にして、ユーザー アカウントごとにセカンダリ認証方式を構成します。MFA が有効になっていることをユーザーに知らせ、その要件 (サインインにスマートフォンを使用することを義務付けるなど) をユーザーが理解し、正常にログインできるようにしてください。

詳細については、[多要素認証の計画](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)を参照してください。

>[!Note]
>Microsoft Office 2010 以前や Apple Mail などの一部のアプリケーションでは MFA を使用できません。このようなアプリを使用するには、従来のパスワードの代わりに「アプリ パスワード」を使用する必要があります。アプリ パスワードでは、アプリが MFA をバイパスして処理を続行できます。アプリ パスワードについては、「[Office 365 のアプリ パスワードを作成する](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)」を参照してください。
>

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: 多要素認証](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-mfa)を確認できます。



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>資格情報が侵害されないように保護する

*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*

このセクションでは、資格情報が侵害されないように保護するポリシーを構成する方法を学習します。攻撃者は組織のクラウド サービスとデータにアクセスするため、ユーザーのアカウント名とパスワードを突き止めて、資格情報を侵害しようとします。 Azure AD Identity Protection は、攻撃者が複数のアカウントやグループを横方向に移動し、最終的に最も重要なデータにたどり着くのを防ぐさまざまな方法を提供します。

Azure AD Identity Protection では次の作業を実行できます。

|||
|:---------|:---------|
|組織の ID における潜在的な脆弱性の洗い出しと対処|Azure AD では、機械学習を使用して異常や不審なアクティビティ (サインインとサインイン後の活動など) を検出します。Identity Protection はこのデータを使用して、問題の評価と対処の実施に役立つレポートとアラートを生成します。|
|組織の ID に関連する不審なアクションの検出と自動対応|指定されているリスク レベルに達した時点で、検出された問題に対し自動的に対応するリスクベースのポリシーを構成できます。このリスクベースのポリシーと、Azure Active Directory および Enterprise Mobility + Security (EMS) の他の条件付きアクセス制御との組み合わせにより、自動的にアクセスをブロックするか、または修正処置 (パスワード リセットと後続のサインインでの多要素認証の義務付けなど) を実行することができます。|
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

