---
title: Microsoft 365 テナントへのユーザー サインインの保護
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/16/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: ユーザーが多要素認証（MFA）およびその他の機能を使用して安全にサインインすることを要求します。
ms.openlocfilehash: 6c8f58e54ae21b4a5e1566dc72673e1d69152863
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132247"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a>Microsoft 365 テナントへのユーザー サインインの保護

ユーザー サインインのセキュリティを強化するには：

- Azure Active Directory（Azure AD）パスワード保護を使用する
- 多要素認証 (MFA) を使用する
- ID とデバイス アクセス ポリシーを展開する

## <a name="azure-ad-password-protection"></a>Azure AD パスワード保護

Azure AD パスワード保護は、既知の脆弱なパスワードとそのバリアントを検出してブロックし、組織固有の脆弱な用語もブロックできます。 既定のグローバル禁止パスワード リストは、Azure AD テナントのすべてのユーザーに自動的に適用されます。 カスタムの禁止パスワード リストに追加のエントリを定義できます。 ユーザーがパスワードを変更またはリセットすると、これらの禁止パスワード リストがチェックされ、強力なパスワードの使用が強制されます。

詳細については、[Azure AD パスワード保護の設定](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)を参照してください。

## <a name="mfa"></a>MFA

MFA では、ユーザーのサインインは、ユーザー アカウントのパスワード以外に追加の検証を受ける必要があります。 悪意のあるユーザーがユーザー アカウントのパスワードを決定した場合でも、アクセスが許可される前にスマートフォンに送信されるテキスト メッセージなど、追加の検証に応答できる必要があります。

![正しいパスワードと追加認証によりサインインが成功する](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

MFA を使用するための最初の手順は、***すべての管理者アカウント（特権アカウント）に MFA を要求する***ことです。

この最初の手順以外にも、マイクロソフトはすべてのユーザーに MFA を強くお勧めします。

Microsoft 365 プランに基づき管理者またはユーザーに MFA の使用を要求する方法は3つあります。

| プラン | 推奨事項 |
|---------|---------|
|Microsoft 365 のすべてのプラン (Azure AD Premium P1 または P2 ライセンスなし)     |[Azure AD でセキュリティの既定値を有効にします](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD のセキュリティの既定値には、ユーザーと管理者用の MFA が含まれています。   |
|Microsoft 365 E3 (Azure AD Premium P1 ライセンスを含む)     | [一般的な条件付きアクセス ポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用して、次のポリシーを構成します。 <br>- [管理者に MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [すべてのユーザーに MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [従来の認証をブロックする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (Azure AD Premium P2 ライセンスを含む)     | Azure AD Identity Protection を利用して、次の 2 つのポリシーを作成して、Microsoft の[条件付きアクセスと関連ポリシーの推奨されるセット](../enterprise/identity-access-policies.md)の実装を開始します。<br> - [サインインのリスクが中、または高のときに MFA を要求する](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [高リスク ユーザーはパスワードを変更する必要がある](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

### <a name="security-defaults"></a>セキュリティの既定値

セキュリティの既定値は、2019 年 10 月 21 日以降に作成された Microsoft 365 および Office 365 の有料または試用版サブスクリプションの新機能です。 これらのサブスクリプションではセキュリティの既定値がオンになっており、***すべてのユーザーが Microsoft Authenticator アプリで MFA を使用する必要があります***。
 
ユーザーは、スマートフォンから Microsoft Authenticator アプリを使用して MFA に 14 日間登録できます。これは、セキュリティの既定値が有効になった後、初めてサインインしたときから始まります。 14 日が経過すると、ユーザーは MFA 登録が完了するまでサインインできなくなります。

セキュリティの既定値では、すべての組織が、既定で有効になっているユーザー サインインの基本レベルのセキュリティを確保しています。 条件付きアクセス ポリシーを使用する MFA を優先して、または個々のアカウントに対して、セキュリティの既定値を無効にすることができます。

詳細については、こちらの「[セキュリティの既定値の概要](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。

### <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

条件付きアクセス ポリシーとは、サインインが評価され、アクセスが許可される条件を指定する一連のルールです。 たとえば、次のような条件付きアクセス ポリシーを作成できます。

- ユーザー アカウント名が Exchange、ユーザー、パスワード、セキュリティ、SharePoint、またはグローバル管理者の役割を割り当てられたユーザーのグループのメンバーである場合、アクセスを許可する前に MFA が必要です。

このポリシーを使用すると、これらの管理者の役割から割り当てられたり、または割り当てられなかったりした場合に、個別のユーザー アカウントを MFA 用に構成しようとするのではなく、グループ メンバーシップに基づいて MFA を要求することができるようになります。

条件付きアクセス ポリシーを使用して、Windows 10 を実行しているノート PC などの準拠デバイスからサインインする必要があるなど、より高度な機能を使用することもできます。

条件付きアクセスには、Microsoft 365 E3 および E5 に含まれている Azure AD Premium P1 ライセンスが必要です。

詳細については、こちらの[条件付きアクセスの概要](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)を参照してください。

### <a name="using-these-methods-together"></a>これらの方法を組み合わせて使用する

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

## <a name="identity-and-device-access-policies"></a>ID とデバイスのアクセス ポリシー

ID とデバイス アクセスの設定とポリシーとは、特定のアクセス要求を許可するかどうか、およびどのような条件下で許可するかを決定する条件付きアクセス、Intune、およびAzure AD Identity Protection ポリシーと組み合わせて推奨される必須機能とその設定です。 この決定は、サインインのユーザーアカウント、使用しているデバイス、ユーザーがアクセスに使用しているアプリ、アクセス要求が行われた場所、および要求のリスクの評価に基づいています。 この機能により、承認されたユーザーとデバイスのみが重要なリソースにアクセスできるようになります。

>[!Note]
>Azure AD Identity Protection には、Microsoft 365 E5 に含まれている Azure AD Premium P2 ライセンスが必要です。
>

ID とデバイスのアクセス ポリシーは、3つの層で使用するように定義されています。 

- ベースライン保護とは、アプリとデータにアクセスするID とデバイスの最小レベルのセキュリティです。
- 機密保護は、特定のデータに追加のセキュリティを提供します。 ID とデバイスは、より高いレベルのセキュリティとデバイスの正常性要件の対象です。
- 高度に規制または分類されたデータが存在する環境の保護は、通常、高度に分類されている、企業秘密が含まれている、またはデータ規制の対象となる少量のデータ用です。 ID とデバイスは、より高いレベルのセキュリティとデバイスの正常性用件の対象です。 

これらの層とそれに対応する構成は、データ、ID、およびデバイス全体で一貫したレベルの保護を提供します。

マイクロソフトは、Microsoft Teams、Exchange Online、SharePointの特定の設定を含む、組織内のID とデバイスのアクセス ポリシーを構成および展開することを強くお勧めします。 詳細については、[ID とデバイスのアクセス設定](microsoft-365-policies-configurations.md)を参照してください。

<!--

## Let your users reset their own passwords

Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff. Users can quickly reset their passwords at any time and from any place. Watch [this video](https://go.microsoft.com/fwlink/?linkid=2128524) to set up SSPR.

## Sign in to SaaS apps with Azure AD

In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud. By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for your users to discover the applications they need and sign into them securely.

## Results of deployment of secure sign-ins

After deployment of MFA, your users:

- Are required to use MFA for sign-ins.
- Have completed the MFA registration process and are using MFA for all sign-ins.
- Can use SSPR to reset their own passwords.

- [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)

--> 

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a>MFA と安全なサインインのための管理技術リソース

- [MFA for Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [Microsoft 365 の ID ロードマップ](identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD トレーニング ビデオ](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Azure 多要素認証の登録ポリシーの構成](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [ID とデバイスのアクセス構成](microsoft-365-policies-configurations.md)

