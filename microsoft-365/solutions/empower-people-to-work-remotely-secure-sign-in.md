---
title: ステップ 1. MFA を使用してハイブリッド ワーカーのサインイン セキュリティを強化する
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: ハイブリッド ワーカーが多要素認証 (MFA) でサインインすることを要求します。
ms.openlocfilehash: d59f990cd7acf576247d75e6544ad045179e3c81
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189050"
---
# <a name="step-1-increase-sign-in-security-for-hybrid-workers-with-mfa"></a>ステップ 1. MFA を使用してハイブリッド ワーカーのサインイン セキュリティを強化する

ハイブリッド ワーカーのサインインのセキュリティを強化するには、多要素認証 (MFA) を使用します。 MFA では、ユーザーのサインインは、ユーザー アカウントのパスワード以外に追加の検証を受ける必要があります。 悪意のあるユーザーがユーザー アカウントのパスワードを決定した場合でも、アクセスが許可される前にスマートフォンに送信されるテキスト メッセージなど、追加の検証に応答できる必要があります。

![正しいパスワードと追加認証によりサインインが成功します。](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

ハイブリッド ワーカー、特に管理者を含むすべてのユーザーに対して、Microsoft は MFA を強くお勧めします。

Microsoft 365 プランに基づいてユーザーに MFA の使用を要求する方法は 3 つあります。

|プラン  |推奨事項  |
|---------|---------|
|Microsoft 365 のすべてのプラン (Azure AD Premium P1 または P2 ライセンスなし)     |[Azure AD でセキュリティの既定値を有効にします](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD のセキュリティの既定値には、ユーザーと管理者用の MFA が含まれています。   |
|Microsoft 365 E3 (Azure AD Premium P1 ライセンスを含む)     | [一般的な条件付きアクセス ポリシー](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用して、次のポリシーを構成します。 <br>- [管理者に MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [すべてのユーザーに MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [従来の認証をブロックする](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (Azure AD Premium P2 ライセンスを含む)     | Azure AD Identity Protection を活用して、次のポリシーを作成することで、Microsoft の[条件付きアクセスと関連ポリシーの推奨セット](../security/office-365-security/identity-access-policies.md)の実装を開始します。<br> - [サインインのリスクが中、または高のときに MFA を要求する](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [先進認証をサポートしないクライアントはブロックする](../security/office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br>- [高リスク ユーザーはパスワードを変更する必要がある](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>セキュリティの既定値

セキュリティの既定値は、2019 年 10 月 21 日以降に作成された Microsoft 365 および Office 365 の有料または試用版サブスクリプションの新機能です。 これらのサブスクリプションではセキュリティの既定値がオンになっており、***すべてのユーザーが Microsoft Authenticator アプリで MFA を使用する必要があります***。
 
ユーザーは、スマートフォンから Microsoft Authenticator アプリを使用して MFA に 14 日間登録できます。これは、セキュリティの既定値が有効になった後、初めてサインインしたときから始まります。 14 日が経過すると、ユーザーは MFA 登録が完了するまでサインインできなくなります。

セキュリティの既定値では、すべての組織が、既定で有効になっているユーザー サインインの基本レベルのセキュリティを確保しています。 条件付きアクセス ポリシーを使用する MFA を優先して、または個々のアカウントに対して、セキュリティの既定値を無効にすることができます。

詳細については、こちらの「[セキュリティの既定値の概要](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。

## <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

条件付きアクセス ポリシーは、サインインが評価および許可される条件を指定する一連のルールです。 たとえば、次のような条件付きアクセス ポリシーを作成できます。

- ユーザー アカウント名が Exchange、ユーザー、パスワード、セキュリティ、SharePoint、またはグローバル管理者の役割を割り当てられたユーザーのグループのメンバーである場合、アクセスを許可する前に MFA が必要です。

このポリシーを使用すると、これらの管理者の役割から割り当てられたり、または割り当てられなかったりした場合に、個別のユーザー アカウントを MFA 用に構成しようとするのではなく、グループ メンバーシップに基づいて MFA を要求することができるようになります。

条件付きアクセス ポリシーを使用して、Windows 10 を実行しているノート PC などの準拠デバイスからサインインする必要があるなど、より高度な機能を使用することもできます。

条件付きアクセスには、Microsoft 365 E3 および E5 に含まれている Azure AD Premium P1 ライセンスが必要です。

詳細については、こちらの「[条件付きアクセスの概要](/azure/active-directory/conditional-access/overview)」を参照してください。

## <a name="azure-ad-identity-protection-support"></a>Azure AD Identity Protection のサポート

Azure AD Identity Protection を使用すると、次のような追加の条件付きアクセス ポリシーを作成することができます。

- サインインのリスクが中または高であると判断された場合、MFA が必要です。

Azure AD Identity Protection には、Microsoft 365 E5 に含まれている Azure AD Premium P2 ライセンスが必要です。

詳細については、「[Risk-based Conditional Access (リスク ベースの条件付きアクセス)](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users)」を参照してください。

Azure AD Identity Protection を使用すると、ユーザーに MFA への登録を要求するポリシーを作成することもできます。 詳細については、「[Azure AD 多要素認証の登録ポリシーの構成](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)」を参照してください。


## <a name="using-these-methods-together"></a>これらの方法を組み合わせて使用する

以下の点にご注意ください。

- 条件付きアクセス ポリシーを有効にしている場合、セキュリティの既定値を有効にすることはできません。
- セキュリティの既定値を有効にしている場合は、条件付きアクセス ポリシーを有効にすることはできません。

セキュリティの既定値が有効になっている場合、すべての新しいユーザーは MFA 登録と Microsoft Authenticator アプリの使用を求められます。 

この表は、セキュリティの既定値と条件付きアクセス ポリシーで MFA を有効にした結果を示しています。

| メソッド | Enabled | 無効 | 追加の認証方法 |
|:-------|:-----|:-------|:-------|
| **セキュリティの既定値**  | 条件付きアクセス ポリシーを使用できない | 条件付きアクセス ポリシーを使用できる | Microsoft Authenticator アプリ |
| **条件付きアクセス ポリシー** | いずれかが有効になっている場合、セキュリティの既定値を有効にすることはできません | すべてが無効になっている場合は、セキュリティの既定値を有効にすることができます  | MFA 登録中にユーザーが指定  |
||||

## <a name="let-your-users-reset-their-own-passwords"></a>ユーザーが自分でパスワードをリセットできるようにする

セルフサービスによるパスワードのリセット (SSPR) は、IT スタッフに影響を与えることなく、ユーザーが自分のパスワードをリセットできるようにします。 ユーザーは、いつでもどこからでも自分のパスワードをすばやくリセットすることができます。 詳細については、「[Azure AD のセルフサービスによるパスワードのリセットの展開を計画する](/azure/active-directory/authentication/howto-sspr-deployment)」を参照してください。

## <a name="sign-in-to-saas-apps-with-azure-ad"></a>Azure AD で SaaS アプリにサインインする

クラウド認証をユーザーに提供するだけでなく、Azure AD はすべてのアプリをオンプレミスにしているか、Microsoft のクラウドにあるか、または別のクラウドにあるかどうかに関係なく、全てのアプリを保護する中心的な方法にもなります。 [アプリケーションを Azure AD - Microsoft Azure Actuve Directoryに統合する](/azure/active-directory/manage-apps/plan-an-application-integration)と、ハイブリッド ワーカーが必要なアプリケーションを見つけて安全にサインインするのが簡単になります。

## <a name="admin-technical-resources-for-mfa-and-identity"></a>MFA と ID のための管理技術リソース

- [Azure AD がリモート作業を可能にするのに役立つ 5 つの方法](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Microsoft 365 の ID ロードマップ](../enterprise/identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD トレーニング ビデオ](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)

## <a name="results-of-step-1"></a>手順 1 の結果

MFA の展開後、ユーザーは次のことを行います。

- サインインに MFA を使用する必要があります。
- MFA 登録プロセスを完了し、すべてのサインインに MFA を使用します。
- SSPR を使用して自分のパスワードをリセットすることができます。

## <a name="next-step"></a>次のステップ

[![手順 2: オンプレミスのアプリとサービスへのリモート アクセスを提供する。](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)

[手順 2](empower-people-to-work-remotely-remote-access.md) に進み、オンプレミスのアプリとサービスへのリモート アクセスを提供します。