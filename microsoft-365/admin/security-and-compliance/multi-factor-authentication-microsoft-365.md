---
title: Microsoft 365の多要素認証
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: 多要素認証 (MFA) では、強力である必要があるパスワードと追加の検証方法の両方が使用されます。
ms.openlocfilehash: cabb7d3efc6d99c69e7e125c9170ac7367fc3929
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66044062"
---
# <a name="multifactor-authentication-for-microsoft-365"></a>Microsoft 365の多要素認証

パスワードは、コンピューターまたはオンライン サービスへのサインインを認証する最も一般的な方法ですが、最も脆弱です。 ユーザーは、簡単なパスワードを選択して、異なるコンピューターやサービスに対して同じパスワードを使用できます。

サインインのセキュリティを強化するには、多要素認証 (MFA) を使用する必要があります。これは、強力である必要があるパスワードと、次に基づく追加の検証方法の両方を使用します。

- スマートフォンなど、簡単に複製できないもの。
- ユーザーに固有の生物学的特徴 (指紋、顔、または他の生体認証属性など)。

追加の検証方法は、ユーザーのパスワードが確認されるまで使用されません。 MFA を使用すると、強力なユーザー パスワードが侵害された場合でも、攻撃者はスマートフォンやサインインを完了するためのフィンガープリントを持っていません。

## <a name="mfa-support-in-microsoft-365"></a>Microsoft 365 の MFA サポート

既定では、Microsoft 365 および Office 365 は、ユーザー アカウントに対する MFA を次の方法でサポートします。

- 電話に送信される、確認コードの入力に必要なテキスト メッセージ。
- 電話呼び出し。
- Microsoft Authenticator スマート フォン アプリ。

どちらの場合も、MFA サインインでは、追加の検証に "簡単に重複していないものを持っているもの" メソッドを使用します。 Microsoft 365 および Office 365 の MFA は、次の複数の方法で有効にできます。

- セキュリティの既定値を使用する
- 条件付きアクセス ポリシーを使用する
- 個別のユーザー アカウントごとに設定する (推奨されません)

これらの方法は、ご利用の Microsoft 365 プランに応じて決まります。

|計画|推奨事項|お客様の種類|
|---|---|---|
|すべての Microsoft 365 プラン|すべてのユーザー アカウントに対して MFA を要求する、セキュリティの既定値を使用します。 <p> 個々のユーザー アカウントでユーザーごとの MFA を構成することもできますが、これはお勧めしません。|小規模企業|
|Microsoft 365 Business Premium <p> Microsoft 365 E3 <p> Azure Active Directory (Azure AD) Premium P1 ライセンス|グループ メンバーシップ、アプリ、またはその他の条件に基づいてユーザー アカウントに MFA を要求するには、 [セキュリティの既定値または条件付きアクセス ポリシー](/microsoft-365/business-premium/m365bp-conditional-access) を使用します。|小規模企業から大規模企業まで|
|Microsoft 365 E5 <p> Azure AD Premium P2|Azure AD Identity Protection を使用して、サインイン リスクの条件に基づいて MFA を要求します。|大規模企業|
||||

### <a name="security-defaults"></a>セキュリティの既定値

セキュリティの既定値は、2019 年 10 月 21 日以降に作成された Microsoft 365 および Office 365 の有料または試用版サブスクリプションの新機能です。 これらのサブスクリプションでは、次のセキュリティの既定値が有効になっています。

- すべてのユーザーが Microsoft Authenticator アプリで MFA を使用する必要があります。
- 従来の認証をブロックします。

ユーザーは、スマートフォンから Microsoft Authenticator アプリを使用して MFA に 14 日間登録できます。これは、セキュリティの既定値が有効になった後、初めてサインインしたときから始まります。 14 日が経過すると、ユーザーは MFA 登録が完了するまでサインインできなくなります。

セキュリティの既定値では、すべての組織が、既定で有効になっているユーザー サインインの基本レベルのセキュリティを確保しています。 条件付きアクセス ポリシーを使用する MFA を優先して、セキュリティの既定値を無効にすることができます。

Azure ポータル内の Azure AD の **プロパティ** ウィンドウで、セキュリティの既定値を有効または無効にします。

![[ディレクトリのプロパティ] ページの画像。](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

すべての Microsoft 365 プランで、セキュリティの既定値を使用できます。

詳細については、こちらの「[セキュリティの既定値の概要](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」をご覧ください。

### <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

条件付きアクセス ポリシーは、サインインが評価および許可される条件を指定する一連のルールです。 たとえば、次のような条件付きアクセス ポリシーを作成できます。

- ユーザー アカウント名が Exchange、ユーザー、パスワード、セキュリティ、SharePoint、またはグローバル管理者の役割を割り当てられたユーザーのグループのメンバーである場合、アクセスを許可する前に MFA が必要です。

このポリシーを使用すると、これらの管理者ロールに割り当てられている場合や割り当てられていないときに、MFA の個々のユーザー アカウントを構成しようとするのではなく、グループ メンバーシップに基づいて MFA を要求できます。

また、条件付きアクセス ポリシーを使用して、特定のアプリに対して MFA を要求する、または Windows 10 を実行しているノート PC などの準拠デバイスからのサインインを要求するなど、より高度な機能を使用することもできます。

Azure ポータル内の Azure AD の **セキュリティ** ウィンドウで、条件付きアクセス ポリシーを構成します。

![条件付きアクセスのメニュー オプションの図。](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

条件付きアクセス ポリシーは、次のプランで使用できます。

- Microsoft 365 Business Premium
- Microsoft 365 E3 および E5
- Azure AD Premium P1、Azure AD Premium P2 ライセンス

Microsoft 365 Business Premium を使用している小規模企業の場合、次の手順で、条件付きアクセス ポリシーを簡単に使用できます。

1. MFA を必要とするユーザー アカウントを含むグループを作成します。
2. **グローバル管理者に対して MFA を要求する** ポリシーを有効にします。
3. 次の設定を使用して、グループ ベースの条件付きアクセス ポリシーを作成します
    - 割り当て > ユーザーとグループ: 上記の手順 1 で作成したグループの名前。
    - 割り当て > クラウド アプリまたは操作: すべてのクラウド アプリ。
    - アクセス制御 > 許可 > アクセス権の付与 > 多要素認証を要求する。
4. ポリシーを有効にします。
5. 上記の手順 1 で作成したグループにユーザー アカウントを追加してテストします。
6. 追加のユーザー アカウントに MFA を要求するには、手順 1 で作成したグループに追加します。

この条件付きアクセス ポリシーを使用すると、お客様のペースでユーザーに MFA の要件を展開できます。

大規模企業は、[一般的な条件付きアクセス ポリシー](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用して、次のポリシーを構成する必要があります。

- [管理者に対して MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [すべてのユーザーに対して MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [従来の認証をブロックする](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

詳細については、こちらの[条件付きアクセスの概要](/azure/active-directory/conditional-access/overview)をご覧ください。

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Azure AD Identity Protection を使用すると、追加の条件付きアクセス ポリシーを作成して、[サインインのリスクが中以上のとき MFA を要求する](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)ことができます。

Azure AD Identity Protection とリスク ベースの条件付きアクセス ポリシーは、次のプランで使用できます。

- Microsoft 365 E5
- Azure AD Premium P2

詳細については、こちらの [Azure AD Identity Protection の概要](/azure/active-directory/identity-protection/overview-identity-protection)をご覧ください。

### <a name="legacy-per-user-mfa-not-recommended"></a>レガシユーザーごとの MFA (推奨されません)

セキュリティの既定値または条件付きアクセス ポリシーを使用して、ユーザー アカウントのサインインに MFA を要求する必要があります。ただし、これらのいずれかを使用できない場合、Microsoft では、任意のサイズのサブスクリプションに対して管理者ロール (特にグローバル管理者ロール) を持つユーザー アカウントに対して MFA を強くお勧めします。

Microsoft 365 管理センターの <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**[アクティブ ユーザー**</a>] ウィンドウから、個々のユーザー アカウントに対して MFA を有効にします。

![[アクティブユーザー] ページの [多要素認証] オプションの画像。](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

有効になると、ユーザーが次回サインインすると、MFA の登録と、追加の検証方法の選択とテストを求めるメッセージが表示されます。

### <a name="using-these-methods-together"></a>これらの方法を組み合わせて使用する

この表は、セキュリティの既定値、条件付きアクセス ポリシー、およびユーザーごとのアカウント設定で MFA を有効にした結果を示しています。

|*アイテム*|Enabled|無効|第 2 の認証方法|
|---|---|---|---|
|**セキュリティの既定値**|条件付きアクセス ポリシーを使用できない|条件付きアクセス ポリシーを使用できる|Microsoft Authenticator アプリ|
|**条件付きアクセス ポリシー**|有効になっている場合は、セキュリティの既定値を有効にすることはできません|すべてが無効になっている場合は、セキュリティの既定値を有効にすることができます|MFA 登録中にユーザーが指定|
|**レガシユーザーごとの MFA (推奨されません)**|サインインごとに MFA が必要なセキュリティの既定値と条件付きアクセス ポリシーをオーバーライドします|セキュリティの既定値と条件付きアクセス ポリシーによって上書きされます|MFA 登録中にユーザーが指定|
||||

セキュリティの既定値が有効になっている場合、すべての新しいユーザーは、次回のサインイン時に MFA 登録と Microsoft Authenticator アプリの使用を求められます。

## <a name="ways-to-manage-mfa-settings"></a>MFA 設定を管理する方法

以下の 2 種類の方法で MFA 設定を管理できます。

Azure ポータルでは、次のことができます。

- セキュリティの既定値を有効または無効にする
- 条件付きアクセス ポリシーを構成する

Microsoft 365 管理センターでは、ユーザーごとおよびサービスごとの <a href="https://go.microsoft.com/fwlink/?LinkId=279980" target="_blank">MFA 設定</a>を構成できます。

## <a name="next-steps"></a>次の手順

[Microsoft 365 の MFA を設定する](set-up-multi-factor-authentication.md)

## <a name="related-content"></a>関連コンテンツ

[多要素認証をオンにする](set-up-multi-factor-authentication.md) (ビデオ)\
[スマートフォンの多要素認証をオンにする](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14) (ビデオ)
