---
title: 一般的な ID およびデバイス アクセス ポリシー - エンタープライズ Microsoft 365の|Microsoft Docs
description: 推奨される一般的な ID とデバイス アクセス ポリシーと構成について説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 564747e31f7ab412d14790e42e6c8e901e382de4e08834b9a5b2f7c775454c74
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53816997"
---
# <a name="common-identity-and-device-access-policies"></a>共通 ID とデバイスのアクセス ポリシー

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- Azure

この記事では、Azure Active Directory (Azure AD) アプリケーション プロキシで公開されたオンプレミス アプリケーションなど、Microsoft 365 クラウド サービスへのアクセスをセキュリティで保護するための一般的な推奨ポリシーについて説明します。

このガイダンスでは、新しくプロビジョニングされた環境に推奨ポリシーを展開する方法について説明します。 これらのポリシーを個別のラボ環境で設定すると、事前運用環境と実稼働環境にロールアウトをステージングする前に、推奨されるポリシーを理解して評価できます。 新しくプロビジョニングされた環境は、評価ニーズを反映するためにクラウド専用またはハイブリッドにできます。

## <a name="policy-set"></a>ポリシー セット

次の図は、推奨されるポリシーのセットを示しています。 各ポリシーが適用する保護の層、およびポリシーが PC、電話、タブレット、またはデバイスの両方のカテゴリに適用されるかどうかを示します。 また、これらのポリシーを構成する場所も示します。

[![ID とデバイス アクセスを構成するための一般的なポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)

個々のポリシーへのリンクを含む 1 ページの PDF サマリーを次に示します。

[![手引き資料の ID とデバイス保護用の親指Microsoft 365イメージ](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [PDF として表示する](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \|[PDF としてダウンロードする](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

この記事の残りの部分では、これらのポリシーを構成する方法について説明します。

> [!NOTE]
> Intune にデバイスを登録する前に多要素認証 (MFA) の使用を要求して、デバイスが目的のユーザーを所有することを保証することを推奨します。 デバイス コンプライアンス ポリシーを適用するには、Intune にデバイスを登録する必要があります。

これらのタスクを実行する時間を与えるために、次の表に示す順序でベースライン ポリシーを実装することをお勧めします。 ただし、機密性の高い高度に規制されたレベルの保護に関する MFA ポリシーは、いつでも実装できます。

|保護レベル|ポリシー|詳細|ライセンス|
|---|---|---|---|
|**Baseline**|[サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5またはMicrosoft 365 E3 E5 セキュリティ アドオンを使用する|
||[先進認証をサポートしないクライアントはブロックする](#block-clients-that-dont-support-multi-factor)|最新の認証を使用しないクライアントは条件付きアクセス ポリシーをバイパスできます。そのため、これらをブロックすることが重要です。|Microsoft 365 E3 または E5|
||[高リスク ユーザーはパスワードを変更する必要がある](#high-risk-users-must-change-password)|リスクの高いアクティビティが自分のアカウントで検出された場合、サインイン時にユーザーにパスワードの変更を強制的に行います。|Microsoft 365 E5またはMicrosoft 365 E3 E5 セキュリティ アドオンを使用する|
||[アプリケーション保護ポリシー (APP) データ保護の適用](#apply-app-data-protection-policies)|プラットフォームごとに 1 つの Intune アプリ保護ポリシー (Windows iOS/iPadOS、Android)。|Microsoft 365 E3 または E5|
||[承認済みアプリとアプリ保護を要求する](#require-approved-apps-and-app-protection)|iOS、iPadOS、または Android を使用して携帯電話とタブレットに対してモバイル アプリ保護を適用します。|Microsoft 365 E3 または E5|
||[デバイス コンプライアンス ポリシーの定義](#define-device-compliance-policies)|プラットフォームごとに 1 つのポリシー。|Microsoft 365 E3 または E5|
||[準拠 PC が必要](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|アプリまたは macOS を使用して PC の Intune Windows適用します。|Microsoft 365 E3 または E5|
|**機密**|[サインイン リスクが低い、中程度、または高い場合に MFA *を要求**する*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5またはMicrosoft 365 E3 E5 セキュリティ アドオンを使用する|
||[準拠している PC とモバイル *デバイスを* 要求する](#require-compliant-pcs-and-mobile-devices)|Pc (Windows macOS) と電話またはタブレット (iOS、iPadOS、または Android) の両方に Intune 管理を適用します。|Microsoft 365 E3 または E5|
|**厳しく規制**|[*常に* MFA を要求する](#assigning-policies-to-groups-and-users)||Microsoft 365 E3 または E5|
|

## <a name="assigning-policies-to-groups-and-users"></a>グループとユーザーへのポリシーの割り当て

ポリシーを構成する前に、保護層AD使用している Azure グループを特定します。 通常、ベースライン保護は組織内のすべてのユーザーに適用されます。 ベースライン保護と機密性の高い保護の両方に含まれるユーザーには、すべてのベースライン ポリシーと機密ポリシーが適用されます。 保護は累積的であり、最も制限の厳しいポリシーが適用されます。

条件付きアクセスの除外用に Azure ADグループを作成する方法をお勧めします。 [割り当て] セクションの [ユーザーとグループ] 設定の [除外] 値で、すべての条件付きアクセス ポリシーにこのグループ **を追加** します。 これにより、アクセスの問題のトラブルシューティング中にユーザーにアクセスを提供する方法が提供されます。 これは一時的なソリューションとしてのみお勧めします。 このグループで変更を監視し、除外グループが意図した方法でのみ使用されている必要があります。

MFA を要求するグループの割り当てと除外の例を次に示します。

![MFA ポリシーのグループ割り当てと除外の例](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

結果は次のとおりです。

- サインイン リスクが中程度または高の場合は、すべてのユーザーが MFA を使用する必要があります。

- Executive Staff グループのメンバーは、サインイン リスクが低、中、高の場合に MFA を使用する必要があります。

  この場合、Executive Staff グループのメンバーは、ベースライン ポリシーと機密性の高い条件付きアクセス ポリシーの両方と一致します。 両方のポリシーのアクセス制御が組み合わされ、この場合は機密の条件付きアクセス ポリシーと同じです。

- X グループのトップ シークレット Projectは常に MFA を使用する必要があります

  この場合、トップ シークレット グループ X グループProject、ベースラインポリシーと高度に規制された条件付きアクセス ポリシーの両方が一致します。 両方のポリシーのアクセス制御が組み合わされます。 高度に規制された条件付きアクセス ポリシーのアクセス制御は制限が厳しいため、使用されます。

グループとユーザーに高レベルの保護を適用する場合は注意が必要です。 たとえば、トップ シークレット Project X グループのメンバーは、Project X の厳しく規制されたコンテンツで作業していない場合でも、サインインの度に MFA を使用する必要があります。

これらの推奨事項のAD作成された Azure のすべてのグループは、そのグループとしてMicrosoft 365があります。 これは、ドキュメントをセキュリティで保護する際に、Microsoft Teamsラベルを展開SharePoint。

![グループを作成するMicrosoft 365例](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>サインイン リスクに基づいて MFA を要求する

使用を要求する前に、ユーザーに MFA を登録する必要があります。 E5 セキュリティ アドオンを使用する Microsoft 365 E5、Microsoft 365 E3、EMS E5 を使用した Office 365、または個々の Azure AD Premium P2 ライセンスがある場合は、Azure AD Identity Protection で MFA 登録ポリシーを使用して、ユーザーが MFA に登録するように要求できます。 前提条件 [となる作業には、](identity-access-prerequisites.md) すべてのユーザーを MFA に登録する作業が含まれます。

ユーザーが登録された後、新しい条件付きアクセス ポリシーを使用してサインインに MFA を要求できます。

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。
2. Azure サービスの一覧で、[次へ]**をAzure Active Directory。**
3. [管理] **リストで** 、[セキュリティ] **を選択し**、[条件付きアクセス] **を選択します**。
4. [ **新しいポリシー] を** 選択し、新しいポリシーの名前を入力します。

次の表では、サインイン リスクに基づいて MFA を要求する条件付きアクセス ポリシー設定について説明します。

[割り **当て] セクションで、次の設定を** 行います。

|Setting|[プロパティ]|値|注|
|---|---|---|---|
|ユーザーとグループ|含める|**[ユーザーとグループ] >グループ** を選択する: 対象のユーザー アカウントを含む特定のグループを選択します。|パイロット ユーザー アカウントを含むグループから開始します。|
||除外|**ユーザーとグループ**: 条件付きアクセス例外グループを選択します。サービス アカウント (アプリ ID)。|メンバーシップは、必要に応じて一時的に変更する必要があります。|
|クラウド アプリまたはアクション|**クラウド アプリ >含む**|**[アプリの選択**]: このポリシーを適用するアプリを選択します。 たとえば、[設定] をExchange Online。||
|条件|||環境とニーズに固有の条件を構成します。|
||サインイン リスク||次の表のガイダンスを参照してください。|
|

### <a name="sign-in-risk-condition-settings"></a>サインインリスク条件の設定

対象とする保護レベルに基づいてリスク レベルの設定を適用します。

|保護のレベル|必要なリスク レベルの値|アクション|
|---|---|---|
|基準|高、中|両方を確認します。|
|機密|高、中、低|3 つすべてがチェックされます。|
|厳しく規制||MFA を常に適用するには、すべてのオプションをオフのままにします。|
|

[アクセス制御 **] セクションで、次の操作を** 行います。

|Setting|[プロパティ]|値|アクション|
|---|---|---|---|
|許可|**Grant access**||選択|
|||**多要素認証を要求する**|小切手|
||**選択したコントロールすべてが必要**||選択|
|

[選択 **] を** 選択して[付与] **設定を保存** します。

最後に、[ポリシーの有効化 **] で [オン****] を選択** し、[作成] を **選択します**。

また、[What [if] ツールを使用して](/azure/active-directory/active-directory-conditional-access-whatif) ポリシーをテストする方法も検討してください。

## <a name="block-clients-that-dont-support-multi-factor"></a>多要素をサポートしないクライアントをブロックする

多要素認証をサポートしないクライアントをブロックするには、条件付きアクセス ポリシーのこれらの表の設定を使用します。

多[要素認証を](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)サポートするクライアントのMicrosoft 365については、この記事を参照してください。

[割り **当て] セクションで、次の設定を** 行います。

|Setting|[プロパティ]|値|注|
|---|---|---|---|
|ユーザーとグループ|含める|**[ユーザーとグループ] >グループ** を選択する: 対象のユーザー アカウントを含む特定のグループを選択します。|パイロット ユーザー アカウントを含むグループから開始します。|
||除外|**ユーザーとグループ**: 条件付きアクセス例外グループを選択します。サービス アカウント (アプリ ID)。|メンバーシップは、必要に応じて一時的に変更する必要があります。|
|クラウド アプリまたはアクション|**クラウド アプリ >含む**|**[アプリの** 選択]: 最新の認証をサポートしていないクライアントに対応するアプリを選択します。||
|条件|**クライアント アプリ**|[構成 **] で [はい** ] を **選択します。** <p> ブラウザーとモバイル アプリと **デスクトップ クライアント****のチェック マークを解除する**||
|

[アクセス制御 **] セクションで、次の操作を** 行います。

|Setting|[プロパティ]|値|アクション|
|---|---|---|---|
|許可|**アクセスをブロックする**||選択|
||**選択したコントロールすべてが必要**||選択|
|

[選択 **] を** 選択して[付与] **設定を保存** します。

最後に、[ポリシーの有効化 **] で [オン****] を選択** し、[作成] を **選択します**。

What if ツール [を使用して](/azure/active-directory/active-directory-conditional-access-whatif) ポリシーをテストする方法を検討してください。

このExchange Online、認証ポリシーを使用して基本認証を無効に[](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)し、すべてのクライアント アクセス要求で最新の認証を使用できます。

## <a name="high-risk-users-must-change-password"></a>高リスク ユーザーはパスワードを変更する必要がある

サインイン時に、危険度の高いユーザーのすべての侵害されたアカウントが強制的にパスワード変更を実行することを確認するには、次のポリシーを適用する必要があります。

管理者資格情報を使用して [Microsoft Azure ポータル (https://portal.azure.com)](https://portal.azure.com/) にログインしてから、**[Azure AD Identity Protection]、[ユーザーのリスク ポリシー]** の順に移動します。

[割り **当て] セクションで、次の設定を** 行います。

|型|[プロパティ]|値|アクション|
|---|---|---|---|
|Users|含める|**すべてのユーザー**|選択|
|ユーザーのリスク|**High**||選択|
|

2 番目の **[割り当て] セクションで、次の設定を** 行います。

|型|[プロパティ]|値|アクション|
|---|---|---|---|
|Access|**SSL 経由でのみ**||選択|
|||**パスワードの変更を必須とする**|小切手|
|

[完了 **] を** 選択して、アクセス設定 **を** 保存します。

最後に、[ポリシーの適用 **] で [オン****] を選択** し、[保存] を **選択します**。

What if ツール [を使用して](/azure/active-directory/active-directory-conditional-access-whatif) ポリシーをテストする方法を検討してください。

このポリシーを Configure [Azure AD](/azure/active-directory/authentication/concept-password-ban-bad)パスワード保護と組み合わせて使用します。このポリシーは、既知の脆弱なパスワードとそのバリアント、および組織固有の追加の弱い用語を検出してブロックします。 Azure ADパスワード保護を使用すると、変更されたパスワードが強力なパスワードになります。

## <a name="apply-app-data-protection-policies"></a>APP データ保護ポリシーの適用

APP は、許可するアプリと、組織のデータに対して実行できるアクションを定義します。 APP で使用できる選択肢により、組織は特定のニーズに合わせて保護を調整できます。 一部のユーザーにとって、完全なシナリオを実装するために必要なポリシー設定が明らかではない場合があります。 組織がモバイル クライアント エンドポイントの強化を優先するために、Microsoft は iOS および Android モバイル アプリ管理用の APP データ保護フレームワークに分類を導入しました。

APP データ保護フレームワークは、3 つの異なる構成レベルに編成され、各レベルは前のレベルから構築されます。

- **Enterpriseデータ保護**(レベル 1) を使用すると、アプリは PIN で保護され、暗号化され、選択的ワイプ操作が実行されます。 Android デバイスの場合、このレベルは Android デバイス構成証明を検証します。 これは、メールボックス ポリシーで同様のデータ保護制御を提供し、IT とユーザー Exchange Onlineを APP に導入するエントリ レベルの構成です。
- **Enterprise強化されたデータ保護**(レベル 2) では、APP データ漏洩防止メカニズムと最小 OS 要件が導入されています。 これは、仕事や学校のデータにアクセスするほとんどのモバイル ユーザーに適用される構成です。
- **Enterprise保護**(レベル 3) では、高度なデータ保護メカニズム、強化された PIN 構成、および APP Mobile Threat Defense が導入されています。 この構成は、リスクの高いデータにアクセスしているユーザーにとって望ましい構成です。

各構成レベルの特定の推奨事項と、保護する必要がある最小アプリを確認するには、アプリ保護ポリシーを使用したデータ保護フレームワーク [を確認してください](/mem/intune/apps/app-protection-framework)。

「Identity and device [access configurations」](microsoft-365-policies-configurations.md)で概説されている原則を使用して、ベースラインおよび機密保護層は、レベル 2 エンタープライズ拡張データ保護設定と密接にマップされます。 高度に規制された保護層は、レベル 3 エンタープライズの高データ保護設定に密接にマップされます。

|保護レベル|アプリ保護ポリシー|詳細|
|---|---|---|
|基準|[レベル 2 の拡張データ保護](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|レベル 2 で適用されるポリシー設定には、レベル 1 に推奨されるポリシー設定すべてが含まれています。以下のポリシー設定に追加または更新して、レベル 1 よりも多くのコントロールとより高度な構成を実装します。|
|機密|[レベル 2 の拡張データ保護](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|レベル 2 で適用されるポリシー設定には、レベル 1 に推奨されるポリシー設定すべてが含まれています。以下のポリシー設定に追加または更新して、レベル 1 よりも多くのコントロールとより高度な構成を実装します。|
|規制の厳しい|[レベル 3 エンタープライズの高データ保護](/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|レベル 3 で適用されるポリシー設定には、レベル 1 とレベル 2 に推奨されるポリシー設定すべてが含まれます。以下のポリシー設定に追加または更新して、レベル 2 よりも多くのコントロールとより高度な構成を実装します。|
|

データ保護フレームワークの設定を使用して、Microsoft エンドポイント マネージャープラットフォーム (iOS と Android) ごとに新しいアプリ保護ポリシーを作成するには、次の方法を実行します。

1. 「アプリ保護ポリシーを作成して展開する方法」の手順に従って、ポリシー[を手動で作成](/mem/intune/apps/app-protection-policies)Microsoft Intune。
2. Intune の [PowerShell スクリプトを](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) 使用して、サンプルの Intune アプリ保護ポリシー構成フレームワーク JSON [テンプレートをインポートします](https://github.com/microsoftgraph/powershell-intune-samples)。

## <a name="require-approved-apps-and-app-protection"></a>承認済みアプリと APP 保護を要求する

Intune で適用した APP 保護ポリシーを適用するには、条件付きアクセス ポリシーを作成して、承認済みのクライアント アプリと APP 保護ポリシーで設定された条件を要求する必要があります。

アプリ保護ポリシーを適用するには、「条件付きアクセスによるクラウド アプリ アクセスのアプリ保護ポリシーを要求する」で説明されている一連のポリシーが [必要です](/azure/active-directory/conditional-access/app-protection-based-conditional-access)。 これらのポリシーは、それぞれ、この推奨される ID およびアクセス構成ポリシーセットに含まれています。

承認済みアプリと APP 保護を必要とする条件付きアクセス ポリシーを作成するには、「シナリオ 1: Microsoft 365 アプリでアプリ保護ポリシーを使用して承認されたアプリを必要としますが、Exchange ActiveSync クライアントが Exchange Online に接続することをブロックする OAuth 対応の Exchange ActiveSync クライアントをブロックするシナリオ[1: Microsoft 365](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)Outlook の Azure AD 条件付きアクセス ポリシーを構成する」に従います。

   > [!NOTE]
   > このポリシーにより、モバイル ユーザーは該当するアプリを使用Officeすべてのエンドポイントにアクセスできます。

モバイル アクセスを有効にしている場合は、Exchange Online [ActiveSync](secure-email-recommended-policies.md#block-activesync-clients)クライアントを実装します。これは、基本認証を利用しているクライアントが Exchange ActiveSync クライアントに接続Exchange Online。 このポリシーは、この記事の上部にある図には示されません。 電子メールのセキュリティ保護に関する [ポリシーの推奨事項で説明され、説明されています](secure-email-recommended-policies.md)。

iOS と Android 用エッジを必要とする条件付きアクセス ポリシーを作成するには、「シナリオ[2:](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-2-browser-apps-require-approved-apps-with-app-protection-policies)ブラウザー アプリでアプリ保護ポリシーが承認されているアプリが必要です。これにより、エッジ for iOS と Android は許可されますが、他のモバイル デバイス Web ブラウザーが Microsoft 365 エンドポイントに接続することをブロックする」の「手順 2: Microsoft 365 の Azure AD 条件付きアクセス ポリシーを構成する」に従います。

 これらのポリシーは、許可コントロールを利用します [[承認済みクライアント アプリ](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) を必要とする] と [アプリ保護 [ポリシーを要求する] を使用します](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)。

最後に、iOS および Android デバイス上の他のクライアント アプリの従来の認証をブロックすると、これらのクライアントは条件付きアクセス ポリシーをバイパスできません。 この記事のガイダンスに従っている場合は、最新の認証をサポートしていないクライアントのブロックを既 [に構成しています](#block-clients-that-dont-support-multi-factor)。

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>デバイス コンプライアンス ポリシーの定義

デバイス コンプライアンス ポリシーは、デバイスが準拠と判断するために満たす必要がある要件を定義します。 Intune デバイス コンプライアンス ポリシーは、管理センター内Microsoft エンドポイント マネージャー作成します。

PC、電話、またはタブレット プラットフォームごとにポリシーを作成する必要があります。

- Android デバイス管理者
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1以降
- Windows 10以降

デバイス コンプライアンス ポリシーを作成するには、管理者資格情報を使用して Microsoft エンドポイント マネージャー [管理](https://endpoint.microsoft.com)センターにログインし、[デバイス コンプライアンスポリシー ポリシー] に \>  \> **移動します**。 [ポリシー **の作成] を選択します**。

デバイス コンプライアンス ポリシーを展開するには、ユーザー グループに割り当てる必要があります。 ポリシーを作成して保存した後で、ポリシーを割り当てる。 管理センターでポリシーを選択し、[割り当て] **を選択します**。 ポリシーを受信するグループを選択した後、[保存] を **選択して、** そのグループの割り当てを保存し、ポリシーを展開します。

Intune でコンプライアンス ポリシーを作成する手順については、「Intune ドキュメントの[](/mem/intune/protect/create-compliance-policy)「コンプライアンス ポリシーを作成する」を参照Microsoft Intuneを参照してください。

### <a name="recommended-settings-for-ios"></a>iOS の推奨設定

iOS/iPadOS では、次の 2 つの登録シナリオがサポートされています。このフレームワークの一部として以下の 2 つが対象となります。

- [個人所有デバイスのデバイス登録](/mem/intune/enrollment/ios-enroll) – これらのデバイスは個人所有であり、仕事と個人の両方の使用に使用されます。
- [企業所有のデバイス](/mem/intune/enrollment/device-enrollment-program-enroll-ios) の監視された自動デバイス登録 - これらのデバイスは企業所有であり、1 人のユーザーに関連付けされ、個人の使用ではなく仕事専用に使用されます。

iOS/iPadOS セキュリティ構成フレームワークは、いくつかの異なる構成シナリオに編成され、個人所有デバイスと監視デバイスのガイダンスを提供します。

個人所有のデバイスの場合:

- 基本セキュリティ (レベル 1) – ユーザーが仕事や学校のデータにアクセスする個人用デバイスの最小セキュリティ構成として、この構成をお勧めします。 これは、パスワード ポリシー、デバイス ロックの特性を適用し、特定のデバイス機能 (信頼されていない証明書など) を無効にすることで行われます。
- セキュリティの強化 (レベル 2) – ユーザーが機密情報や機密情報にアクセスするデバイスに対して、この構成をお勧めします。 この構成は、データ共有コントロールを制定します。 この構成は、デバイス上の仕事または学校のデータにアクセスするほとんどのモバイル ユーザーに適用されます。
- セキュリティの高い (レベル 3) – 一意にリスクが高い特定のユーザーまたはグループが使用するデバイス (権限のない開示によって組織に大いなる損失が発生する機密性の高いデータを処理するユーザー) に対して、この構成をお勧めします。 この構成は、より強力なパスワード ポリシーを制定し、特定のデバイス機能を無効にし、追加のデータ転送制限を適用します。

監視対象デバイスの場合:

- 基本セキュリティ (レベル 1) – ユーザーが仕事や学校のデータにアクセスする監視対象デバイスの最小セキュリティ構成として、この構成をお勧めします。 これは、パスワード ポリシー、デバイス ロックの特性を適用し、特定のデバイス機能 (信頼されていない証明書など) を無効にすることで行われます。
- セキュリティの強化 (レベル 2) – ユーザーが機密情報や機密情報にアクセスするデバイスに対して、この構成をお勧めします。 この構成は、データ共有コントロールを制定し、USB デバイスへのアクセスをブロックします。 この構成は、デバイス上の仕事または学校のデータにアクセスするほとんどのモバイル ユーザーに適用されます。
- セキュリティの高い (レベル 3) – 一意にリスクが高い特定のユーザーまたはグループが使用するデバイス (権限のない開示によって組織に大いなる損失が発生する機密性の高いデータを処理するユーザー) に対して、この構成をお勧めします。 この構成は、より強力なパスワード ポリシーを制定し、特定のデバイス機能を無効にし、追加のデータ転送制限を適用し、Apple のボリューム購入プログラムを通じてアプリをインストールする必要があります。

「Identity and device [access configurations」](microsoft-365-policies-configurations.md)で説明されている原則を使用して、基準計画と機密性の高い保護層は、レベル 2 の強化されたセキュリティ設定と密接にマップされます。 高度に規制された保護層は、レベル 3 の高セキュリティ設定に密接にマップされます。

|保護レベル  |デバイス ポリシー |詳細  |
|---------|---------|---------|
|基準     |セキュリティの強化 (レベル 2)         |レベル 2 で適用されるポリシー設定には、レベル 1 に推奨されるポリシー設定すべてが含まれています。以下のポリシー設定に追加または更新して、レベル 1 よりも多くのコントロールとより高度な構成を実装します。         |
|機密     |セキュリティの強化 (レベル 2)         |レベル 2 で適用されるポリシー設定には、レベル 1 に推奨されるポリシー設定すべてが含まれています。以下のポリシー設定に追加または更新して、レベル 1 よりも多くのコントロールとより高度な構成を実装します。         |
|規制の厳しい     |高セキュリティ (レベル 3)         |レベル 3 で適用されるポリシー設定には、レベル 1 とレベル 2 に推奨されるポリシー設定すべてが含まれます。以下のポリシー設定に追加または更新して、レベル 2 よりも多くのコントロールとより高度な構成を実装します。         |

各構成レベルの特定のデバイスコンプライアンスとデバイス制限の推奨事項を確認するには [、iOS/iPadOS セキュリティ構成フレームワークを確認してください](/mem/intune/enrollment/ios-ipados-configuration-framework)。

### <a name="recommended-settings-for-android"></a>Android の推奨設定

Android Enterpriseはいくつかの登録シナリオをサポートします。このフレームワークの一部として次の 2 つが対象となります。

- [Android Enterpriseプロファイル](/intune/android-work-profile-enroll)– この登録モデルは、通常、個人所有のデバイスで使用され、IT は作業データと個人データの明確な分離境界を提供します。 IT によって制御されるポリシーは、作業データを個人プロファイルに転送できないことを確認します。
- [Android Enterprise](/intune/android-fully-managed-enroll)完全に管理されたデバイス – これらのデバイスは、企業所有であり、1 人のユーザーに関連付け、仕事用として使用され、個人の使用には使用されません。

Android Enterprise構成フレームワークは、いくつかの異なる構成シナリオに編成され、作業プロファイルと完全に管理されたシナリオに関するガイダンスを提供します。

Android Enterpriseプロファイル デバイスの場合:

- 作業プロファイルの基本的なセキュリティ (レベル 1) – ユーザーが仕事や学校のデータにアクセスする個人用デバイスの最小セキュリティ構成として、この構成をお勧めします。 この構成では、パスワード要件が導入され、作業データと個人データが分離され、Android デバイス構成証明が検証されます。
- ワーク プロファイルのセキュリティの高い (レベル 3) – 特定のユーザーまたはグループが一意にリスクが高いデバイス (権限のない開示によって組織に大いなる損失が発生する機密性の高いデータを処理するユーザー) に対して、この構成をお勧めします。 この構成では、モバイル脅威防御または Microsoft Defender for Endpoint が導入され、Android の最小バージョンを設定し、より強力なパスワード ポリシーを制定し、作業と個人の分離をさらに制限します。

Android の場合Enterprise完全に管理されたデバイスの場合:

- 完全に管理された基本セキュリティ (レベル 1) – エンタープライズ デバイスの最小セキュリティ構成としてこの構成を推奨します。 この構成は、仕事や学校のデータにアクセスするほとんどのモバイル ユーザーに適用されます。 この構成では、パスワード要件が導入され、Android の最小バージョンが設定され、特定のデバイス制限が適用されます。
- 完全に管理された拡張セキュリティ (レベル 2) – ユーザーが機密情報または機密情報にアクセスするデバイスに対して、この構成をお勧めします。 この構成は、より強力なパスワード ポリシーを制定し、ユーザー/アカウント機能を無効にします。
- 完全に管理された高セキュリティ (レベル 3) - 一意にリスクが高い特定のユーザーまたはグループが使用するデバイス (権限のない開示によって組織に大いなる損失が発生する機密性の高いデータを処理するユーザー) に対して、この構成をお勧めします。 この構成により、Android の最小バージョンが増加し、モバイル脅威防御または Microsoft Defender for Endpoint が導入され、追加のデバイス制限が適用されます。

[「Identity](microsoft-365-policies-configurations.md)and device access configurations」で概説されている原則を使用して、Baseline および Sensitive protection tiers は、個人所有デバイスのレベル 1 の基本的なセキュリティと、完全に管理されたデバイスのレベル 2 拡張セキュリティ設定と密接にマップされます。 高度に規制された保護層は、レベル 3 の高セキュリティ設定に密接にマップされます。

Android Enterpriseプロファイル デバイスの場合:

|保護レベル  |デバイス ポリシー |詳細  |
|---------|---------|---------|
|基準     |作業プロファイル: 基本セキュリティ (レベル 1)      |該当なし         |
|機密     |作業プロファイル: 基本セキュリティ (レベル 1)         |該当なし         |
|基準     |完全管理: 拡張セキュリティ (レベル 2)       |レベル 2 で適用されるポリシー設定には、レベル 1 に推奨されるポリシー設定すべてが含まれています。以下のポリシー設定に追加または更新して、レベル 1 よりも多くのコントロールとより高度な構成を実装します。         |
|機密     |完全管理: 拡張セキュリティ (レベル 2)         |レベル 2 で適用されるポリシー設定には、レベル 1 に推奨されるポリシー設定すべてが含まれています。以下のポリシー設定に追加または更新して、レベル 1 よりも多くのコントロールとより高度な構成を実装します。         |
|規制の厳しい     |高セキュリティ (レベル 3)         |レベル 3 で適用されるポリシー設定には、レベル 1 とレベル 2 に推奨されるポリシー設定すべてが含まれます。以下のポリシー設定に追加または更新して、レベル 2 よりも多くのコントロールとより高度な構成を実装します。         |

各構成レベルの特定のデバイスコンプライアンスとデバイス制限の推奨事項を確認するには[、Android Enterpriseセキュリティ構成フレームワークを確認してください](/mem/intune/enrollment/android-configuration-framework)。

### <a name="recommended-settings-for-windows-10-and-later"></a>ユーザーおよび以降のWindows 10設定

ポリシー作成プロセスの手順 **2:** コンプライアンス設定で構成されている、Windows 10以降を実行している PC では、次の設定が推奨されます。

[**デバイスの正常性> Windows正常性構成証明サービスの評価ルール** については、次の表を参照してください。

|プロパティ|値|アクション|
|---|---|---|
|BitLocker を要求する|必須|選択|
|デバイスでセキュア ブートを有効にする必要がある|必須|選択|
|コードの整合性を要求する|必須|選択|
|

[ **デバイスのプロパティ]** で、IT およびセキュリティ ポリシーに基づいてオペレーティング システムのバージョンに適切な値を指定します。

[Configuration **Manager コンプライアンス] で、[** 要求] **を選択します**。

システム **セキュリティについては、** 次の表を参照してください。

|型|[プロパティ]|値|アクション|
|---|---|---|---|
|パスワード|モバイル デバイスのロックを解除するためにパスワードを要求する|必須|選択|
||単純なパスワード|ブロック|選択|
||パスワードの種類|デバイスの既定値|選択|
||パスワードの最小文字数|6 |種類|
||パスワードが必要になる前の最大非アクティブ時間 (分)|15|種類 <p> この設定は、Android バージョン 4.0 以上または KNOX 4.0 以上でサポートされています。 iOS デバイスの場合、iOS 8.0 以上でサポートされています。|
||パスワードの有効期限 (日)|41|種類|
||再利用を防止する以前のパスワードの数|5 |種類|
||デバイスがアイドル状態から戻る際にパスワードを要求する (Mobile および Holographic)|必須|Windows 10以降に使用可能|
|暗号化|デバイス上のデータ ストレージの暗号化|必須|選択|
|デバイス セキュリティ|ファイアウォール|必須|選択|
||ウイルス対策|必須|選択|
||スパイウェア対策|必須|選択 <p> この設定には、セキュリティ センターに登録されているスパイウェア対策Windows セキュリティ必要です。|
|Defender|Microsoft Defender マルウェア対策|必須|選択|
||Microsoft Defender マルウェア対策の最小バージョン||種類 <p> デスクトップでのみWindows 10されます。 Microsoft では、最新バージョンから 5 つ以下のバージョンをお勧めします。|
||Microsoft Defender マルウェア対策の署名を最新の情報に更新する|必須|選択|
||リアルタイム保護|必須|選択 <p> デスクトップでのみWindows 10|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

|型|[プロパティ]|値|アクション|
|---|---|---|---|
|Microsoft Defender for Endpoint rules in the Microsoft エンドポイント マネージャー センター|[デバイスがコンピューター リスク スコアの下にあるか、または下にある必要がある](/mem/intune/protect/advanced-threat-protection-configure#create-and-assign-compliance-policy-to-set-device-risk-level)|中|選択|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>準拠している PC を必要とします (ただし、準拠していない電話とタブレット)

準拠している PC を要求するポリシーを追加する前に、Intune で管理用にデバイスを登録してください。 デバイスが意図したユーザーを所有しているという保証のために、デバイスを Intune に登録する前に、多要素認証を使用することを推奨します。

準拠している PC を要求するには、次の操作を行います。

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。
2. Azure サービスの一覧で、[次へ]**をAzure Active Directory。**
3. [管理] **リストで** 、[セキュリティ] **を選択し**、[条件付きアクセス] **を選択します**。
4. [ **新しいポリシー] を** 選択し、新しいポリシーの名前を入力します。

5. [ **割り当て]** で、[ **ユーザーとグループ]** を選択し、ポリシーを適用するユーザーを含める。 条件付きアクセス除外グループも除外します。

6. [割 **り当て] で**、[ **クラウド アプリまたはアクション] を選択します**。

7. [ **含める**] で、[アプリの選択 **>選択**] を選択し、[クラウド アプリ] リストから目的のアプリ **を選択** します。 たとえば、[設定] をOffice 365。 [完了 **時に選択** ] を選択します。

8. 準拠している PC (ただし、準拠していない電話とタブレット)を要求するには、[割り当て] で、[デバイス プラットフォームの>**を選択します**。 [構成 **] で [はい** ] **を選択します**。 [  **デバイス プラットフォームの選択]** を選択し、[ **は** い] を選択して [任意のデバイス] **を選択し** 、[除外] で **[iOS** と **Android** の選択] を選択し、[完了] を **選択します**。

9. [アクセス **制御] で、[** 許可] **を選択します** 。

10. [ **アクセスを許可する] を** 選択し、[デバイスを **準拠としてマークする] をオンにします**。 複数のコントロールの場合は、[すべての **選択したコントロールを要求する] を選択します**。 完了したら、[選択] **を選択します**。

11. [ポリシー **の有効化** ] **で [オン]** を選択し、[作成] を **選択します**。

> [!NOTE]
> このポリシーを有効にする前に、デバイスが準拠している必要があります。 それ以外の場合は、ユーザー アカウントが条件付きアクセス除外グループに追加されるまで、ロックアウトされ、このポリシーを変更できません。

## <a name="require-compliant-pcs-and-mobile-devices"></a>準拠している PC とモバイル *デバイスを* 要求する

すべてのデバイスのコンプライアンスを要求するには、次の操作を行います。

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。
2. Azure サービスの一覧で、[次へ]**をAzure Active Directory。**
3. [管理] **リストで** 、[セキュリティ] **を選択し**、[条件付きアクセス] **を選択します**。
4. [ **新しいポリシー] を** 選択し、新しいポリシーの名前を入力します。

5. [ **割り当て]** で、[ **ユーザーとグループ]** を選択し、ポリシーを適用するユーザーを含める。 条件付きアクセス除外グループも除外します。

6. [割 **り当て] で**、[ **クラウド アプリまたはアクション] を選択します**。

7. [ **含める**] で、[アプリの選択 **>選択**] を選択し、[クラウド アプリ] リストから目的のアプリ **を選択** します。 たとえば、[設定] をOffice 365。 [完了 **時に選択** ] を選択します。

8. [アクセス **制御] で、[** 許可] **を選択します** 。

9. [ **アクセスを許可する] を** 選択し、[デバイスを **準拠としてマークする] をオンにします**。 複数のコントロールの場合は、[すべての **選択したコントロールを要求する] を選択します**。 完了したら、[選択] **を選択します**。

10. [ポリシー **の有効化** ] **で [オン]** を選択し、[作成] を **選択します**。

> [!NOTE]
> このポリシーを有効にする前に、デバイスが準拠している必要があります。 それ以外の場合は、ユーザー アカウントが条件付きアクセス除外グループに追加されるまで、ロックアウトされ、このポリシーを変更できません。

## <a name="next-step"></a>次の手順

[![手順 3: ゲストユーザーと外部ユーザーのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[ゲストユーザーと外部ユーザーのポリシー推奨事項の詳細](identity-access-policies-guest-access.md)