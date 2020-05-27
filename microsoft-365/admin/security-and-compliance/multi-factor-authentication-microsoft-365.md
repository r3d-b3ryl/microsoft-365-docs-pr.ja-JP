---
title: Microsoft 365 の多要素認証
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 での多要素認証について説明します。
ms.openlocfilehash: eba9ae38dbc17a22abb5d5ef92b8cd30a827ae11
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371454"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a>Microsoft 365 の多要素認証

パスワードは、コンピューターまたはオンラインサービスへのサインインを認証する最も一般的な方法ですが、最も脆弱なものでもあります。 ユーザーは、簡単なパスワードを選択したり、複数のサインインに同じパスワードを使用して異なるコンピュータやサービスに対して使用したりすることができます。

サインインのセキュリティレベルを追加するには、多要素認証 (MFA) を使用する必要があります。これには、パスワード (強力なものにする必要があります) と、次のものに基づく追加の検証方法を使用する必要があります。

- スマートフォンなどの、簡単には再現できないものがあります。
- 個人で biologically したもの、指紋、顔、その他のバイオメトリクス属性など。

追加の認証方法は、ユーザーのパスワードが確認されるまで使用されません。 MFA では、強力なユーザーパスワードが侵害された場合でも、攻撃者はスマートフォンや指紋を持ってサインインを完了できません。

## <a name="mfa-support-in-microsoft-365"></a>Microsoft 365 での MFA サポート
既定では、Microsoft 365 と Office 365 はどちらも、次のものを使用するユーザーアカウントに対して MFA をサポートしています。

- ユーザーが確認コードを入力する必要がある、電話に送信されるテキストメッセージ。
- 通話。
- Microsoft Authenticator スマートフォンアプリ。

いずれの場合も、MFA サインインは、追加の確認のための "簡単には複製されていないものがあります" という方法を使用しています。
Microsoft 365 および Office 365 で MFA を有効にするには、複数の方法があります。

- セキュリティの既定値
- 条件付きアクセスポリシーを使用する
- 個別のユーザーアカウントごと (推奨されません)

これらの方法は、Microsoft 365 プランに基づいています。
    
|プラン  |推奨事項  | 顧客の種類 |
|---------|---------|----------|
| すべての Microsoft 365 プラン | セキュリティの既定値を使用します。これには、すべてのユーザーアカウントに対して MFA が必要です。 <br> ユーザーごとのアカウントごとに MFA を要求することもできますが、この方法はお勧めしません。 | Small Business |
| Microsoft 365 Business Premium <br><br> Microsoft 365 E3 <br><br> Azure Active Directory (Azure AD) プレミアム P1 ライセンス | 条件付きアクセスポリシーを使用して、グループメンバーシップ、アプリ、またはその他の条件に基づいてユーザーアカウントに MFA を要求します。 | 小規模企業からエンタープライズへ |
| Microsoft 365 E5 <br><br> Azure AD Premium P2 ライセンス | Azure AD Identity Protection を使用して、サインインリスク基準に基づいて MFA を要求します。 |  Enterprise |
||||

### <a name="security-defaults"></a>セキュリティの既定値

セキュリティの既定値は、2019 年 10 月 21 日以降に作成された Microsoft 365 および Office 365 の有料または試用版サブスクリプションの新機能です。 これらのサブスクリプションのセキュリティの既定値は、次のとおりです。

- すべてのユーザーに対して、Microsoft Authenticator アプリで MFA を使用することを要求します。
- 従来の認証をブロックします。

ユーザーは、スマートフォンから Microsoft Authenticator アプリを使用して MFA に 14 日間登録できます。これは、セキュリティの既定値が有効になった後、初めてサインインしたときから始まります。 14 日が経過すると、ユーザーは MFA 登録が完了するまでサインインできなくなります。

セキュリティの既定値では、すべての組織が、既定で有効になっているユーザー サインインの基本レベルのセキュリティを確保しています。 セキュリティの既定値を無効にして、条件付きアクセスポリシーを使用して MFA を優先させることができます。

Azure ポータルの Azure AD の [**プロパティ**] ウィンドウで、セキュリティの既定値を有効または無効にします。

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

Microsoft 365 プランでは、セキュリティの既定値を使用できます。

詳細については、こちらの「[セキュリティの既定値の概要](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」をご覧ください。 

### <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

条件付きアクセス ポリシーは、サインインが評価および許可される条件を指定する一連のルールです。 たとえば、次のような条件付きアクセス ポリシーを作成できます。

- ユーザーアカウント名が、Exchange、user、password、security、SharePoint、または全体管理者の役割を割り当てられているユーザーのグループのメンバーである場合は、アクセスを許可する前に MFA を必要とします。

このポリシーを使用すると、これらの管理者の役割に割り当てられるか、または割り当てが解除された場合に、MFA の個々のユーザーアカウントを構成しなくても、グループのメンバーシップに基づいて MFA を要求できます。

また、条件付きアクセスポリシーを使用して、特定のアプリに MFA を要求したり、準拠デバイス (Windows 10 を実行しているラップトップなど) からサインインしたりするなど、より高度な機能を提供することもできます。

Azure portal で Azure AD の [**セキュリティ**] ウィンドウから条件付きアクセスポリシーを構成します。

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

条件付きアクセスポリシーは、次の方法で使用できます。

- Microsoft 365 Business Premium
- Microsoft 365 E3 および E5
- Azure AD Premium P1 と Azure AD プレミアム P2 ライセンス 

Microsoft 365 Business Premium を使用する小規模な企業では、次の手順を使用して、条件付きアクセスポリシーを簡単に使用できます。

1. MFA を必要とするユーザーアカウントを含むグループを作成します。
2. [**グローバル管理者の MFA を必要と**する] ポリシーを有効にします。
3. 次の設定を使用して、グループベースの条件付きアクセスポリシーを作成します。
    - ユーザーおよびグループ > の割り当て: 上記の手順1でグループの名前を指定します。
    - クラウドアプリまたはアクション > の割り当て: すべてのクラウドアプリ。
    - アクセス権の付与には、多要素認証を必要と > アクセス許可 > 付与する > を制御します。
4. ポリシーを有効にします。
5. 上記の手順1で作成したグループにユーザーアカウントを追加してテストします。
6. 追加のユーザーアカウントに MFA を要求するには、手順1で作成したグループに MFA を追加します。

この条件付きアクセスポリシーを使用すると、ユーザーに対して MFA の要件を自分のペースでロールアウトできます。

企業では、次のポリシーを構成するために、[一般的な条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用する必要があります。

- [管理者に MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [すべてのユーザーに MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [従来の認証をブロックする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

詳細については、「[条件付きアクセスの概要](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)」をご覧ください。

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Azure AD Identity Protection を使用すると、[サインインリスクが中または高の場合に、MFA を必要と](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)する追加の条件付きアクセスポリシーを作成できます。

Azure AD Id 保護とリスクベースの条件付きアクセスポリシーは、次の方法で使用できます。

- Microsoft 365 E5
- Azure AD Premium P2 ライセンス

詳細については、この「[Azure AD Identity Protection の概要](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)」をご覧ください。

### <a name="mfa-for-an-individual-user-account-not-recommended"></a>個別のユーザーアカウントの MFA (推奨されません)

ユーザーアカウントのサインインに MFA を必要とするには、セキュリティの既定値または条件付きアクセスポリシーを使用する必要があります。ただし、これらのいずれかを使用できない場合は、管理者の役割、特に全体管理者の役割を持つユーザーアカウントに対して、任意のサイズのサブスクリプションに対して MFA を強くお勧めします。 

Microsoft 365 管理センターの**アクティブなユーザー**ウィンドウから、個々のユーザーアカウントに対して MFA を有効にします。

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

有効にすると、ユーザーが次回サインインしたときに、MFA を登録し、追加の検証方法を選択してテストするように求めるメッセージが表示されます。

### <a name="using-these-methods-together"></a>これらの方法を一緒に使用する

この表は、セキュリティの既定値、条件付きアクセス ポリシー、およびユーザーごとのアカウント設定で MFA を有効にした結果を示しています。

|| Enabled | 無効 | 第 2 の認証方法 |
|:-------|:-----|:-------|:-------|
| **セキュリティの既定値** | 条件付きアクセス ポリシーを使用できない |   条件付きアクセス ポリシーを使用できる | Microsoft Authenticator アプリ |
| **条件付きアクセス ポリシー** |いずれかが有効になっている場合、セキュリティの既定値を有効にすることはできません | すべての設定が無効になっている場合は、セキュリティの既定値を有効にできます。 | MFA への登録時にユーザー指定 |
| **ユーザーごとのアカウントの設定 (推奨されません)** | 各サインインで MFA を必要とするセキュリティの既定値と条件付きアクセスポリシーを上書きします。 | セキュリティの既定値と条件付きアクセスポリシーによって上書きされます。 | MFA への登録時にユーザー指定|
||||

セキュリティの既定値が有効になっている場合は、すべての新規ユーザーが MFA 登録を求め、次のサインイン時に Microsoft Authenticator アプリを使用するように求められます。

## <a name="ways-to-manage-mfa-settings"></a>MFA 設定を管理する方法

MFA の設定を管理する方法は2つあります。

Azure portal では、次のことを行うことができます。

- セキュリティの既定値を有効または無効にする
- 条件付きアクセスポリシーを構成する

Microsoft 365 管理センターでは、ユーザー単位およびサービスの MFA 設定を構成できます。

## <a name="your-next-step"></a>次の手順

[Microsoft 365 の MFA をセットアップする](set-up-multi-factor-authentication.md)

