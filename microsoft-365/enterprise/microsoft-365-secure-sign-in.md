---
title: '手順 3: あなたの Microsoft 365 ユーザー アカウントを保護する'
f1.keywords:
- NOCSH
author: kelleyvice-msft
ms.author: kvice
manager: scotv
ms.date: 09/30/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365initiative-coredeploy
- m365solution-m365-identity
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
description: ユーザーが多要素認証（MFA）およびその他の機能を使用して安全にサインインすることを要求します。
ms.openlocfilehash: 56ccd1df24bbfb09920cb0c7138ed2e5dc9ca3cb
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66749970"
---
# <a name="step-3-protect-your-microsoft-365-user-accounts"></a>手順 3: あなたの Microsoft 365 ユーザー アカウントを保護する

ユーザー サインインのセキュリティを強化するには：

- Windows Hello for Business を使用する
- Azure Active Directory（Azure AD）パスワード保護を使用する
- 多要素認証 (MFA) を使用する
- ID とデバイスのアクセス構成を展開する
- Azure AD Identity Protection で資格情報を侵害から保護する

## <a name="windows-hello-for-business"></a>Windows Hello for Business

Windows 10 Enterprise の Windows Hello for Business では、Windows デバイスにサインオンするときのパスワードを強力な 2 要素認証に置き換えます。 この 2 要素認証は、デバイスと生体認証または PIN に関連付けられる新しい種類のユーザー資格情報です。

詳しくは、「[Windows Hello for Business の概要](/windows/security/identity-protection/hello-for-business/hello-overview)」をご覧ください。


## <a name="azure-ad-password-protection"></a>Azure AD パスワード保護

Azure AD パスワード保護は、既知の脆弱なパスワードとそのバリアントを検出してブロックし、組織固有の脆弱な用語もブロックできます。 既定のグローバル禁止パスワード リストは、Azure AD テナントのすべてのユーザーに自動的に適用されます。 カスタムの禁止パスワード リストに追加のエントリを定義できます。 ユーザーがパスワードを変更またはリセットすると、これらの禁止パスワード リストがチェックされ、強力なパスワードの使用が強制されます。

詳細については、[Azure AD パスワード保護の設定](/azure/active-directory/authentication/concept-password-ban-bad)を参照してください。

## <a name="mfa"></a>MFA

MFA では、ユーザーのサインインは、ユーザー アカウントのパスワード以外に追加の検証を受ける必要があります。 悪意のあるユーザーがユーザー アカウントのパスワードを決定した場合でも、アクセスが許可される前にスマートフォンに送信されるテキスト メッセージなど、追加の検証に応答できる必要があります。

![正しいパスワードと追加認証によりサインインが成功します。](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

MFA を使用するための最初の手順は、[すべての管理者アカウント（特権アカウント）に MFA を要求する](protect-your-global-administrator-accounts.md)ことです。 この最初の手順以外にも、Microsoft はすべてのユーザーに MFA をお勧めします。

Microsoft 365 プランに基づいてユーザーに MFA の使用を要求する方法は 3 つあります。

| プラン | 推奨事項 |
|---------|---------|
|Microsoft 365 のすべてのプラン (Azure AD Premium P1 または P2 ライセンスなし)     |[Azure AD でセキュリティの既定値を有効にします](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD のセキュリティの既定値には、ユーザーと管理者用の MFA が含まれています。   |
|Microsoft 365 E3 (Azure AD Premium P1 ライセンスを含む)     | [共通の条件付きアクセス ポリシー](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用して、次のポリシーを構成します: <br>- [管理者に MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [すべてのユーザーに MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [従来の認証をブロックする](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (Azure AD Premium P2 ライセンスを含む)     | Azure AD Identity Protection を利用して、次の 2 つのポリシーを作成し、Microsoft の条件付きアクセスと関連したポリシーの推奨セットの実装を開始します:<br> - [サインインのリスクが中、または高のときに MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk) <br>- [高リスク ユーザーはパスワードを変更する必要がある](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk-user)       |
| | |

### <a name="security-defaults"></a>セキュリティの既定値

セキュリティの既定値は、2019 年 10 月 21 日以降に作成された Microsoft 365 および Office 365 の有料または試用版サブスクリプションの新機能です。 これらのサブスクリプションではセキュリティの既定値がオンになっており、***すべてのユーザーが Microsoft Authenticator アプリで MFA を使用する必要があります***。
 
ユーザーは、スマートフォンから Microsoft Authenticator アプリを使用して MFA に 14 日間登録できます。これは、セキュリティの既定値が有効になった後、初めてサインインしたときから始まります。 14 日が経過すると、ユーザーは MFA 登録が完了するまでサインインできなくなります。

セキュリティの既定値では、すべての組織が、既定で有効になっているユーザー サインインの基本レベルのセキュリティを確保しています。 条件付きアクセス ポリシーを使用する MFA を優先して、または個々のアカウントに対して、セキュリティの既定値を無効にすることができます。

詳細については、「[セキュリティの既定値の概要](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。

### <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

条件付きアクセス ポリシーとは、サインインが評価され、アクセスが許可される条件を指定する一連のルールです。 たとえば、次のような条件付きアクセス ポリシーを作成できます。

- ユーザー アカウント名が Exchange、ユーザー、パスワード、セキュリティ、SharePoint、**Exchange 管理者**、**SharePoint 管理者**、または **グローバル管理者** の役割を割り当てられたユーザーのグループのメンバーである場合、アクセスを許可する前に MFA が必要です。

このポリシーを使用すると、これらの管理者の役割から割り当てられたり、または割り当てられなかったりした場合に、個別のユーザー アカウントを MFA 用に構成しようとするのではなく、グループ メンバーシップに基づいて MFA を要求することができるようになります。

条件付きアクセス ポリシーを使用して、Windows 10 を実行しているノート PC などの準拠デバイスからサインインする必要があるなど、より高度な機能を使用することもできます。

条件付きアクセスには、Microsoft 365 E3 および E5 に含まれている Azure AD Premium P1 ライセンスが必要です。

詳細については、「[条件付きアクセスの概要](/azure/active-directory/conditional-access/overview)」 を参照してください。

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

## <a name="zero-trust-identity-and-device-access-configurations"></a>ゼロ トラスト ID とデバイスのアクセス構成

ゼロ トラスト ID とデバイス アクセス設定とポリシーは、与えられたアクセス要求を付与する必要があるかどうか、またどの条件の下でかを決定する条件付きアクセス、Intune、および Azure AD Identity Protection ポリシーと組み合わせて推奨される前提機能とそれらの設定です。 この決定は、サインインのユーザーアカウント、使用しているデバイス、ユーザーがアクセスに使用しているアプリ、アクセス要求が行われた場所、および要求のリスクの評価に基づいています。 この機能により、承認されたユーザーとデバイスのみが重要なリソースにアクセスできるようになります。

>[!Note]
>Azure AD Identity Protection には、Microsoft 365 E5 に含まれている Azure AD Premium P2 ライセンスが必要です。
>

ID とデバイスのアクセス ポリシーは、3つの層で使用するように定義されています。 

- ベースライン保護とは、アプリとデータにアクセスするID とデバイスの最小レベルのセキュリティです。
- 機密保護は、特定のデータに追加のセキュリティを提供します。 ID とデバイスは、より高いレベルのセキュリティとデバイスの正常性要件の対象です。
- 高度に規制または分類されたデータが存在する環境の保護は、通常、高度に分類されている、企業秘密が含まれている、またはデータ規制の対象となる少量のデータ用です。 ID とデバイスは、より高いレベルのセキュリティとデバイスの正常性用件の対象です。 

これらの層とそれに対応する構成は、データ、ID、およびデバイス全体で一貫したレベルの保護を提供します。

Microsoft では、組織での Microsoft Teams、Exchange Online、および SharePoint の具体的な設定を含むゼロ トラスト ID とデバイス アクセス ポリシーの構成および展開を強くお勧めします。詳細については、「[ゼロ トラスト ID とデバイス アクセス構成](../security/office-365-security/microsoft-365-policies-configurations.md)」を参照してください。

## <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

このセクションでは、資格情報を侵害から保護するポリシーを構成する方法を説明します。資格情報の侵害では、攻撃者がユーザーのアカウント名とパスワードを把握し、組織のクラウド サービスとデータにアクセスします。Azure AD Identity Protection には、攻撃者によるユーザー アカウントの侵害を防ぐための様々な方法が用意されています。

Azure AD Identity Protection では次の作業を実行できます。

|機能|説明|
|:---------|:---------|
| 組織の ID における潜在的な脆弱性の洗い出しと対処 | Azure AD では、機械学習を使用して異常や不審なアクティビティ (サインインとサインイン後の活動など) を検出します。Azure AD Identity Protection はこのデータを使用して、問題の評価と対処の実施に役立つレポートとアラートを生成します。|
|組織の ID に関連する不審なアクションの検出と自動対応|指定されているリスク レベルに達した時点で、検出された問題に対し自動的に対応するリスクベースのポリシーを構成できます。このリスクベースのポリシーと、Azure AD と Microsoft Intune の他の条件付きアクセス制御との組み合わせにより、自動的にアクセスをブロックするか、または修正処置 (パスワード リセットと後続のサインインでの Azure AD 多要素認証の義務付けなど) を実行することができます。 |
| 不審なインシデントを調査し、管理操作によって解決する | セキュリティ インシデントに関する情報を使用して、リスク イベントを調査できます。調査の追跡と修復処理 (パスワードのリセットなど) の開始のための基本的なワークフローを利用できます。 |
|||

[Azure AD Identity Protection の詳細情報](/azure/active-directory/identity-protection/overview-identity-protection)を参照してください。

[Azure AD Identity Protection を有効にする手順](/azure/active-directory/identity-protection/howto-identity-protection-configure-risk-policies)を参照してください。

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a>MFA と安全なサインインのための管理技術リソース

- [MFA for Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [Microsoft 365 ID の展開](deploy-identity-solution-overview.md)
- [Azure Academy Azure AD トレーニング ビデオ](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Azure AD 多要素認証の登録ポリシーの構成](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [ID とデバイスのアクセス構成](../security/office-365-security/microsoft-365-policies-configurations.md)

## <a name="next-step"></a>次のステップ

![ID モデルの展開](../media/deploy-identity-solution-overview/deploy-identity-solution-identity-infrastructure.png)

手順 4 に進み、選択した ID モデルに基づいて ID インフラストラクチャを展開します:

- [クラウド専用 ID](cloud-only-identities.md)
- [ハイブリッド ID](prepare-for-directory-synchronization.md)
