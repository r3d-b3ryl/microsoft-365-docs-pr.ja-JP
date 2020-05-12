---
title: 手順 1. MFA を使用してリモート ワーカーのサインイン セキュリティを強化する
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: リモート ワーカーが多要素認証 (MFA) でサインインすることを要求します。
ms.openlocfilehash: f8154f35baaf693bb51c523cfe4c44374437de02
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003581"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a>手順 1. MFA を使用してリモート ワーカーのサインイン セキュリティを強化する

リモート ワーカーのサインインのセキュリティを強化するには、多要素認証 (MFA) を使用します。 MFA では、ユーザーのサインインは、ユーザー アカウントのパスワード以外に追加の検証を受ける必要があります。 悪意のあるユーザーがユーザー アカウントのパスワードを決定した場合でも、アクセスが許可される前にスマートフォンに送信されるテキスト メッセージなど、追加の検証に応答できる必要があります。

リモート ワーカー、特に管理者を含むすべてのユーザーに対して、Microsoft は MFA を強くお勧めします。

Microsoft 365 プランに基づいてユーザーに MFA の使用を要求する方法は 3 つあります。

|プラン  |推奨事項  |
|---------|---------|
|Microsoft 365 プラン (Azure AD Premium P1 または P2 なし)     |[Azure AD でセキュリティの既定値を有効にします](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD のセキュリティの既定値には、ユーザーと管理者用の MFA が含まれています。   |
|Microsoft 365 E3 (Azure AD Premium P1 搭載)     | [一般的な条件付きアクセス ポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用して、次のポリシーを構成します。 <br>- [管理者に MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [すべてのユーザーに MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [従来の認証をブロックする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (Azure AD Premium P2 搭載)     | Azure AD Identity Protection を利用して、次の 2 つのポリシーを作成して、Microsoft の[条件付きアクセスと関連ポリシーの推奨されるセット](../enterprise/identity-access-policies.md)の実装を開始します。<br> - [サインインのリスクが中、または高のときに MFA を要求する](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [先進認証をサポートしないクライアントはブロックする](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [高リスク ユーザーはパスワードを変更する必要がある](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>セキュリティの既定値

セキュリティの既定値は、2019 年 10 月 21 日以降に作成された Microsoft 365 および Office 365 の有料または試用版サブスクリプションの新機能です。 これらのサブスクリプションではセキュリティの既定値がオンになっており、***すべてのユーザーが Microsoft Authenticator アプリで MFA を使用する必要があります***。
 
ユーザーは、スマートフォンから Microsoft Authenticator アプリを使用して MFA に 14 日間登録できます。これは、セキュリティの既定値が有効になった後、初めてサインインしたときから始まります。 14 日が経過すると、ユーザーは MFA 登録が完了するまでサインインできなくなります。

セキュリティの既定値では、すべての組織が、既定で有効になっているユーザー サインインの基本レベルのセキュリティを確保しています。 条件付きアクセス ポリシーを使用する MFA を優先して、または個々のアカウントに対して、セキュリティの既定値を無効にすることができます。

詳細については、こちらの「[セキュリティの既定値の概要](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」をご覧ください。

## <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

条件付きアクセス ポリシーは、サインインが評価および許可される条件を指定する一連のルールです。 たとえば、次のような条件付きアクセス ポリシーを作成できます。

- ユーザー アカウント名が Exchange、ユーザー、パスワード、セキュリティ、SharePoint、またはグローバル管理者のユーザーの場合、アクセスを許可する前に MFA が必要です。

このポリシーは、これらの管理者の役割に追加または削除されたときに、MFA の個々のユーザー アカウントを忘れずに構成するよりも簡単です。

条件付きアクセス ポリシーを使用して、Windows 10 を実行しているノート PC などの準拠デバイスからサインインする必要があるなど、より高度な機能を使用することもできます。

条件付きアクセスには、Microsoft 365 E3 および E5 に含まれている Azure AD Premium P1 が必要です。

詳細については、「[条件付きアクセスの概要](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)」をご覧ください。

## <a name="azure-ad-identity-protection-policies"></a>Azure AD Identity Protection ポリシー

Azure AD Identity Protection ポリシーは、サインインが評価および許可される条件を指定するルールです。 たとえば、次のような Azure AD Identity Protection ポリシーを作成できます。

- サインインのリスクが中または高であると判断された場合、ユーザーは MFA を使用してサインインする必要があります。

Azure AD Identity Protection には、Microsoft 365 E5 に含まれている Azure AD Premium P2 が必要です。

詳細については、この「[Azure AD Identity Protection の概要](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)」をご覧ください。

## <a name="using-these-methods-together"></a>これらの方法を一緒に使用する

以下の点に注意してください。

- 条件付きアクセス ポリシーを有効にしている場合、セキュリティの既定値を有効にすることはできません。
- セキュリティの既定値を有効にしている場合は、条件付きアクセス ポリシーを有効にすることはできません。

セキュリティの既定値が有効になっている場合、すべての新しいユーザーは MFA 登録と Microsoft Authenticator アプリの使用を求められます。 

この表は、セキュリティの既定値、条件付きアクセス ポリシー、およびユーザーごとのアカウント設定で MFA を有効にした結果を示しています。

|| Enabled | 無効 | 第 2 の認証方法 |
|:-------|:-----|:-------|:-------|
| **セキュリティの既定値**  | 条件付きアクセス ポリシーを使用できない | 条件付きアクセス ポリシーを使用できる | Microsoft Authenticator アプリ |
| **条件付きアクセス ポリシー** | いずれかが有効になっている場合、セキュリティの既定値を有効にすることはできません | すべてが有効になっていない場合は、セキュリティの既定値を有効にできます  | MFA への登録時にユーザー指定  |
||||

## <a name="admin-training-and-technical-resources-for-mfa-and-identity"></a>MFA と ID の管理トレーニングと技術リソース

- [Microsoft 365 の MFA 計画](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-plan)
- [Azure AD がリモート作業を可能にするのに役立つ 5 つの方法](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Microsoft 365 の ID インフラストラクチャを計画および展開する](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [Azure Academy Azure AD トレーニング ビデオ](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Azure 多要素認証の登録ポリシーの構成](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)

## <a name="results-of-step-1"></a>手順 1 の結果

MFA の展開後、ユーザーは次のことを行います。

- サインインに MFA を使用する必要があります。
- MFA 登録プロセスを完了し、すべてのサインインに MFA を使用します。

## <a name="next-step"></a>次の手順

[手順 2](empower-people-to-work-remotely-remote-access.md) に進み、オンプレミスのアプリとサービスへのリモート アクセスを提供します。
