---
title: 共通 ID およびデバイス アクセス ポリシー - Microsoft 365 enterprise |Microsoft Docs
description: 推奨される一般的な ID とデバイスのアクセス ポリシーと構成について説明します。
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
ms.openlocfilehash: 87f064627446a0e41f5ed864c2ae37a2f0e60ba4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286815"
---
# <a name="common-identity-and-device-access-policies"></a>共通 ID とデバイスのアクセス ポリシー

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- Azure

この記事では、Azure Active Directory (Azure AD) アプリケーション プロキシで公開されたオンプレミス アプリケーションを含む、Microsoft 365 クラウド サービスへのアクセスをセキュリティで保護するための一般的な推奨ポリシーについて説明します。

このガイダンスでは、新しくプロビジョニングされた環境で推奨ポリシーを展開する方法について説明します。 これらのポリシーを別のラボ環境で設定すると、運用前環境と実稼働環境へのロールアウトをステージングする前に、推奨されるポリシーを理解して評価できます。 新しくプロビジョニングした環境は、評価のニーズを反映するためにクラウド専用またはハイブリッドの場合があります。

## <a name="policy-set"></a>ポリシー セット

次の図は、推奨される一連のポリシーを示しています。 各ポリシーが適用される保護の層と、ポリシーが PC、電話、タブレットに適用されるかどうか、またはデバイスの両方のカテゴリが表示されます。 また、これらのポリシーを構成する場所も示します。

[![ID とデバイス アクセスを構成するための一般的なポリシー](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

個々のポリシーへのリンクを含む 1 ページの PDF 概要を次に示します。

[![Microsoft 365 のハンドアウトの ID とデバイス保護の親指画像](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [PDF 形式で表示](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \|[PDF としてダウンロードする](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

この記事の残りの部分では、これらのポリシーを構成する方法について説明します。

> [!NOTE]
> デバイスを Intune に登録する前に、多要素認証 (MFA) の使用を要求して、デバイスが意図したユーザーを確実に所有することを保証することを推奨します。 デバイス コンプライアンス ポリシーを適用する前に、Intune にデバイスを登録する必要があります。

これらのタスクを実行する時間を与えるために、次の表に示す順序でベースライン ポリシーを実装することをお勧めします。 ただし、機密レベルと厳しく規制されたレベルの保護のための MFA ポリシーは、いつでも実装できます。

|保護レベル|Policies|詳細情報|
|---|---|---|
|**Baseline**|[サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*](#require-mfa-based-on-sign-in-risk)||
||[先進認証をサポートしないクライアントはブロックする](#block-clients-that-dont-support-multi-factor)|最新の認証を使用しないクライアントは条件付きアクセス ポリシーをバイパスできます。そのため、これらのポリシーをブロックすることが重要です。|
||[高リスク ユーザーはパスワードを変更する必要がある](#high-risk-users-must-change-password)|アカウントに対して危険度の高いアクティビティが検出された場合、サインイン時にユーザーにパスワードの変更を強制的に行います。|
||[アプリ データ保護ポリシーの適用](#apply-app-data-protection-policies)|プラットフォームごとに 1 つの Intune アプリ保護ポリシー (Windows、iOS/iPadOS、Android)。|
||[承認されたアプリとアプリの保護を要求する](#require-approved-apps-and-app-protection)|iOS、iPadOS、または Android を使用して、携帯電話やタブレットにモバイル アプリ保護を適用します。|
||[デバイス コンプライアンス ポリシーの定義](#define-device-compliance-policies)|プラットフォームごとに 1 つのポリシー。|
||[準拠 PC が必要](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Windows または MacOS を使用して PC の Intune 管理を強制します。|
|**機密**|[サインインリスクが低、中 *、高の* 場合 *に* MFA を要求 *する*](#require-mfa-based-on-sign-in-risk)||
||[準拠した PC とモバイル *デバイスが* 必要](#require-compliant-pcs-and-mobile-devices)|PC (Windows または MacOS) と電話またはタブレット (iOS、iPadOS、または Android) の両方に Intune 管理を適用します。|
|**厳しく規制**|[*常に* MFA を要求する](#require-mfa-based-on-sign-in-risk)|
|

## <a name="assigning-policies-to-groups-and-users"></a>グループとユーザーへのポリシーの割り当て

ポリシーを構成する前に、保護の各層AD使用している Azure グループを特定します。 通常、ベースライン保護は組織内のすべてのユーザーに適用されます。 ベースライン保護と機密保護の両方に含まれるユーザーには、すべてのベースライン ポリシーと機密ポリシーが適用されます。 保護は累積的であり、最も制限の厳しいポリシーが適用されます。

条件付きアクセスの除外用に Azure ADグループを作成する方法をお勧めします。 このグループは、[割り当て] セクションの[ユーザーとグループ] 設定の [除外] の値で、すべての条件付きアクセス ポリシー **に追加** します。 これにより、アクセスの問題のトラブルシューティング中にユーザーにアクセスを提供する方法が提供されます。 これは一時的なソリューションとしてのみお勧めします。 このグループの変更を監視し、除外グループが意図した目的にのみ使用されている必要があります。

MFA を要求するグループの割り当てと除外の例を次に示します。

![MFA ポリシーのグループの割り当てと除外の例](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

結果は次のとおりです。

- サインイン リスクが中程度または高の場合、すべてのユーザーは MFA を使用する必要があります。

- エグゼクティブ スタッフ グループのメンバーは、サインインのリスクが低、中、高のときに MFA を使用する必要があります。

  この場合、Executive Staff グループのメンバーは、ベースライン ポリシーと機密性の高い条件付きアクセス ポリシーの両方に一致します。 両方のポリシーのアクセス制御が組み合わされます。この場合、機密性の高い条件付きアクセス ポリシーと同じです。

- [トップ シークレット Project X] グループのメンバーは、常に MFA を使用する必要があります。

  この場合、Top Secret Project X グループのメンバーは、ベースラインポリシーと厳しく規制された条件付きアクセス ポリシーの両方に一致します。 両方のポリシーのアクセス制御が組み合わされます。 厳しく規制された条件付きアクセス ポリシーのアクセス制御は制限が厳しいため、使用されます。

グループやユーザーに高いレベルの保護を適用する場合は注意が必要です。 たとえば、極秘 Project X グループのメンバーは、Project X の厳しく規制されたコンテンツで作業していない場合でも、サインインの度に MFA を使用する必要があります。

これらの推奨事項のAD作成された Azure グループグループはすべて、Microsoft 365 グループとして作成する必要があります。 これは、Microsoft Teams と SharePoint でドキュメントをセキュリティ保護する場合に、区別ラベルを展開する場合に重要です。

![Microsoft 365 グループを作成するための画面キャプチャ](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>サインイン リスクに基づいて MFA を要求する

MFA を使用する前に、ユーザーに MFA を登録する必要があります。 Microsoft 365 E5、IDENTITY & Threat Protection アドオンを持つ Microsoft 365 E3、EMS E5 を使用した Office 365、または個々の Azure AD Premium P2 ライセンスがある場合は、Azure AD Identity Protection で MFA 登録ポリシーを使用して、ユーザーに MFA の登録を要求できます。 前提条件 [となる作業には](identity-access-prerequisites.md) 、すべてのユーザーを MFA に登録する作業が含まれます。

ユーザーが登録された後、新しい条件付きアクセス ポリシーを使用してサインインするために MFA を要求できます。

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。
2. Azure サービスの一覧で、Azure **Active Directory を選択します**。
3. [管理] **ボックスの** 一覧で、[ **セキュリティ] を** 選択し、[条件付きアクセス] **を選択します**。
4. [ **新しいポリシー] を** 選択し、新しいポリシーの名前を入力します。

次の表では、サインイン リスクに基づいて MFA を要求する条件付きアクセス ポリシー設定について説明します。

[割り **当て] セクションで、次の設定を** 行います。

|Setting|[プロパティ]|値|注|
|---|---|---|---|
|ユーザーとグループ|含める|**[ユーザーとグループ] で>グループを選択** する: 対象ユーザー アカウントを含む特定のグループを選択します。|パイロット ユーザー アカウントを含むグループから開始します。|
||除外|**ユーザーとグループ**: 条件付きアクセスの例外グループを選択します。サービス アカウント (アプリ ID)。|メンバーシップは、必要に応じて一時的に変更する必要があります。|
|クラウド アプリまたはアクション|**含めるクラウド >アプリ**|**[アプリの** 選択]: このポリシーを適用するアプリを選択します。 たとえば、[Exchange Online] を選択します。||
|条件|||環境とニーズに固有の条件を構成します。|
||サインイン リスク||次の表のガイダンスを参照してください。|
|

### <a name="sign-in-risk-condition-settings"></a>サインイン リスク条件の設定

対象とする保護レベルに基づいてリスク レベルの設定を適用します。

|保護のレベル|必要なリスク レベルの値|Action|
|---|---|---|
|基準|高、中|両方を確認します。|
|機密|高、中、低|3 つすべて確認します。|
|厳しく規制||常に MFA を適用するには、すべてのオプションをオフのままにします。|
|

[アクセス制御 **] セクションで、次の操作を** 行います。

|Setting|[プロパティ]|値|Action|
|---|---|---|---|
|許可|**Grant access**||Select|
|||**多要素認証を要求する**|小切手|
||**選択したコントロールすべてが必要**||Select|
|

[ **選択] を** 選択して、付与設定 **を保存** します。

最後に、[ポリシーを **有効にする] で [オン** ] **を選択し**、[作成] を **選択します**。

また、What [If ツールを使用して](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) ポリシーをテストすることもできます。

## <a name="block-clients-that-dont-support-multi-factor"></a>多要素をサポートしないクライアントをブロックする

条件付きアクセス ポリシーのこれらの表の設定を使用して、多要素認証をサポートしないクライアントをブロックします。

多 [要素認証を](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) サポートする Microsoft 365 のクライアントの一覧については、この記事を参照してください。

[割り **当て] セクションで、次の設定を** 行います。

|Setting|[プロパティ]|値|注|
|---|---|---|---|
|ユーザーとグループ|含める|**[ユーザーとグループ] で>グループを選択** する: 対象ユーザー アカウントを含む特定のグループを選択します。|パイロット ユーザー アカウントを含むグループから開始します。|
||除外|**ユーザーとグループ**: 条件付きアクセスの例外グループを選択します。サービス アカウント (アプリ ID)。|メンバーシップは、必要に応じて一時的に変更する必要があります。|
|クラウド アプリまたはアクション|**含めるクラウド >アプリ**|**[アプリの** 選択]: 最新の認証をサポートしていないクライアントに対応するアプリを選択します。||
|条件|**クライアント アプリ**|[ **構成] で [はい** ] を選択 **する** <p> ブラウザーおよびモバイル アプリと **デスクトップ クライアント****のチェック マークをオフにします。**||
|

[アクセス制御 **] セクションで、次の操作を** 行います。

|Setting|[プロパティ]|値|Action|
|---|---|---|---|
|許可|**アクセスをブロックする**||Select|
||**選択したコントロールすべてが必要**||Select|
|

[ **選択] を** 選択して、付与設定 **を保存** します。

最後に、[ポリシーを **有効にする] で [オン** ] **を選択し**、[作成] を **選択します**。

What If ツール [を使用して](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) ポリシーをテストする方法を検討してください。

Exchange Online では、認証ポリシーを使用して[](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)基本認証を無効にし、すべてのクライアント アクセス要求で最新の認証を使用できます。

## <a name="high-risk-users-must-change-password"></a>高リスク ユーザーはパスワードを変更する必要がある

すべての危険度の高いユーザーのアカウントがサインイン時に強制的にパスワード変更を実行することを保証するには、次のポリシーを適用する必要があります。

管理者資格情報を使用して [Microsoft Azure ポータル (https://portal.azure.com)](https://portal.azure.com/) にログインしてから、**[Azure AD Identity Protection]、[ユーザーのリスク ポリシー]** の順に移動します。

[割り **当て] セクションで、次の設定を** 行います。

|型|[プロパティ]|値|Action|
|---|---|---|---|
|Users|含める|**[すべてのユーザー]**|Select|
|ユーザーのリスク|**High**||Select|
|

2 番目の **[割り当て] セクションで、次の説明を** 実行します。

|型|[プロパティ]|値|Action|
|---|---|---|---|
|Access|**SSL 経由でのみ**||Select|
|||**パスワードの変更を必須とする**|小切手|
|

[ **完了] を** 選択して Access の設定 **を保存** します。

最後に、ポリシーを **適用するために [オン****] を** 選択し、[保存] を **選択します**。

What If ツール [を使用して](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) ポリシーをテストする方法を検討してください。

このポリシーは [、Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)パスワード保護の構成と組み合わせて使用します。これは、既知の脆弱なパスワードとそのバリアント、および組織に固有の他の脆弱な用語を検出してブロックします。 Azure ADパスワード保護を使用すると、変更されたパスワードが強力なパスワードになります。

## <a name="apply-app-data-protection-policies"></a>アプリ データ保護ポリシーの適用

アプリ保護ポリシー (APP) では、許可するアプリと、アプリが組織のデータに対して実行できるアクションを定義します。 APP で利用できる選択肢により、組織は特定のニーズに合わせて保護を調整できます。 一部のシナリオでは、完全なシナリオを実装するために必要なポリシー設定が明らかではない場合があります。 組織がモバイル クライアント エンドポイントの強化に優先順位を付け支援するために、Microsoft は iOS および Android モバイル アプリ管理用のアプリ データ保護フレームワークの分類を導入しました。

APP データ保護フレームワークは 3 つの異なる構成レベルに編成され、各レベルは前のレベルから構築されます。

- **エンタープライズの基本的なデータ保護** (レベル 1) は、アプリが PIN で保護され、暗号化され、選択的ワイプ操作を実行します。 Android デバイスの場合、このレベルは Android デバイスの構成証明を検証します。 これは、Exchange Online メールボックス ポリシーで同様のデータ保護制御を提供し、IT およびユーザー群を APP に導入するエントリ レベルの構成です。
- **エンタープライズ拡張データ保護** (レベル 2) では、アプリのデータ漏洩防止メカニズムと最小 OS 要件が導入されています。 これは、ほとんどのモバイル ユーザーが仕事や学校のデータにアクセスする場合に適用される構成です。
- **エンタープライズの高データ保護** (レベル 3) では、高度なデータ保護メカニズム、強化された PIN 構成、および APP Mobile Threat Defense が導入されています。 この構成は、リスクの高いデータにアクセスしているユーザーにとって望ましい構成です。

各構成レベルおよび保護する必要がある最小アプリに関する特定の推奨事項を確認するには、アプリ保護ポリシーを使用したデータ保護フレームワーク [を確認してください](https://docs.microsoft.com/mem/intune/apps/app-protection-framework)。

ID とデバイスのアクセス構成[](microsoft-365-policies-configurations.md)に関する原則を使用して、ベースライン層と機密保護層は、レベル 2 エンタープライズ拡張データ保護設定と密接に対応します。 厳しく規制された保護層は、レベル 3 エンタープライズの高いデータ保護設定に密接にマッピングされます。

|保護レベル|アプリ保護ポリシー|詳細情報|
|---|---|---|
|基準|[レベル 2 の拡張データ保護](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|レベル 2 で適用されるポリシー設定には、レベル 1 に推奨されるポリシー設定すべてが含まれます。レベル 1 よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定にのみ追加または更新されます。|
|機密|[レベル 2 の拡張データ保護](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|レベル 2 で適用されるポリシー設定には、レベル 1 に推奨されるポリシー設定すべてが含まれます。レベル 1 よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定にのみ追加または更新されます。|
|厳しく規制|[レベル 3 エンタープライズの高いデータ保護](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|レベル 3 で適用されるポリシー設定には、レベル 1 とレベル 2 に推奨されるポリシー設定すべてが含まれます。レベル 2 よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定のみを追加または更新します。|
|

データ保護フレームワークの設定を使用して、Microsoft Endpoint Manager 内のプラットフォーム (iOS および Android) ごとに新しいアプリ保護ポリシーを作成するには、次の方法を実行します。

1. Microsoft Intune でアプリ保護ポリシーを作成および展開する方法の手順に従って [、ポリシーを手動で作成します](https://docs.microsoft.com/mem/intune/apps/app-protection-policies)。
2. Intune の [PowerShell スクリプトを使用して、サンプル](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) の Intune App Protection Policy Configuration Framework JSON テンプレート [をインポートします](https://github.com/microsoftgraph/powershell-intune-samples)。

## <a name="require-approved-apps-and-app-protection"></a>承認されたアプリとアプリの保護を要求する

Intune で適用したアプリ保護ポリシーを適用するには、条件付きアクセス ポリシーを作成して、承認されたクライアント アプリと APP 保護ポリシーで設定された条件を要求する必要があります。

アプリ保護ポリシーを適用するには、「条件付きアクセスによるクラウド アプリ アクセスのアプリ保護ポリシーを要求する」で説明されている一連のポリシー [が必要です](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)。 これらのポリシーは、それぞれ、この推奨される ID ポリシーとアクセス構成ポリシーのセットに含まれています。

承認されたアプリとアプリ保護を必要とする条件付きアクセス ポリシーを作成するには、シナリオ 1 の「手順 1: Microsoft 365 用の Azure AD 条件付きアクセス ポリシーを構成する」に従います [。Microsoft 365](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)アプリには、iOS および Android 用の Outlook を許可するが、OAuth 対応の Exchange ActiveSync クライアントが Exchange Online に接続することをブロックするアプリ保護ポリシーが必要です。

   > [!NOTE]
   > このポリシーにより、モバイル ユーザーは該当するアプリOfficeすべてのエンドポイントにアクセスできます。

Exchange Online へのモバイル アクセスを有効にする場合は [、ActiveSync](secure-email-recommended-policies.md#block-activesync-clients)クライアントのブロックを実装します。これは、基本認証を利用する Exchange ActiveSync クライアントが Exchange Online に接続するのを防ぐものです。 このポリシーは、この記事の上部にある図には示されません。 電子メールをセキュリティで保護するための [ポリシーの推奨事項に記載されています](secure-email-recommended-policies.md)。

iOS および Android 用の Edge を必要とする条件付きアクセス ポリシーを作成するには、シナリオ 2 の「手順 2: Microsoft [](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-2-browser-apps-require-approved-apps-with-app-protection-policies)365 用の Azure AD 条件付きアクセス ポリシーを構成する」に従います。ブラウザー アプリは、iOS および Android 用の Edge を許可するアプリ保護ポリシーを持つ承認済みアプリを必要としますが、他のモバイル デバイス Web ブラウザーが Microsoft 365 エンドポイントに接続することをブロックします。

 これらのポリシーでは、許可コントロールを利用します。承認されたクライアント [アプリ](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) が必要で、アプリ保護 [ポリシーが必要です](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)。

最後に、iOS および Android デバイス上の他のクライアント アプリのレガシ認証をブロックすることで、これらのクライアントは条件付きアクセス ポリシーをバイパスできません。 この記事のガイダンスに従っている場合は、モダン認証をサポートしていないブロック クライアントが既 [に構成されています](#block-clients-that-dont-support-multi-factor)。

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>デバイス コンプライアンス ポリシーの定義

デバイス コンプライアンス ポリシーは、準拠と判断するためにデバイスが満たす必要がある要件を定義します。 Intune デバイス コンプライアンス ポリシーは、Microsoft Endpoint Manager 管理センター内から作成します。

PC、電話、またはタブレットプラットフォームごとにポリシーを作成する必要があります。

- Android デバイス管理者
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 以降
- Windows 10 以降

デバイス コンプライアンス ポリシーを作成するには、管理者の資格情報を使用して [Microsoft Endpoint Manager 管理](https://endpoint.microsoft.com)センターにログインし、[**デバイス** コンプライアンス ポリシー ポリシー] に \>  \> **移動します**。 [ポリシー **の作成] を選択します**。

デバイス コンプライアンス ポリシーを展開するには、ユーザー グループに割り当てる必要があります。 ポリシーは、作成して保存した後に割り当てる必要があります。 管理センターでポリシーを選択し、[割り当て] **を選択します**。 ポリシーを受信するグループを選択した後、[保存] を **選択して** そのグループ割り当てを保存し、ポリシーを展開します。

Intune でのコンプライアンス ポリシーの作成に関する詳しい手順については、Intune ドキュメントの [「Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) でコンプライアンス ポリシーを作成する」を参照してください。

### <a name="recommended-settings-for-windows-10-and-later"></a>Windows 10 以降の推奨設定

ポリシー作成プロセスの手順 **2:** コンプライアンス設定で構成されている、Windows 10 以降を実行している PC では、次の設定をお勧めします。

Windows **正常性構成証明サービス>の正常性** と評価ルールについては、次の表を参照してください。

|プロパティ|値|Action|
|---|---|---|
|BitLocker が必要|必須|Select|
|デバイスでセキュア ブートを有効にする必要がある|必須|Select|
|コード整合性を要求する|必須|Select|
|

デバイス **のプロパティでは**、IT およびセキュリティ ポリシーに基づいてオペレーティング システムのバージョンに適切な値を指定します。

**Configuration Manager コンプライアンスの場合は、[** 必要] を **選択します**。

システム **セキュリティについては、** 次の表を参照してください。

|型|[プロパティ]|値|Action|
|---|---|---|---|
|Password|モバイル デバイスのロックを解除するためにパスワードを要求する|必須|Select|
||単純なパスワード|ブロック|Select|
||パスワードの種類|デバイスの既定値|Select|
||パスワードの最小文字数|6 |型|
||パスワードが必要になる前の非アクティブ状態の最大時間 (分)|15 |型 <p> この設定は、Android バージョン 4.0 以上または KNOX 4.0 以上でサポートされています。 iOS デバイスでは、iOS 8.0 以上でサポートされています。|
||パスワードの有効期限 (日)|41|型|
||再利用を防止する以前のパスワードの数|5 |型|
||デバイスがアイドル状態から復帰するときにパスワードを要求する (モバイルおよびホログラフィック)|必須|Windows 10 以降で利用可能|
|暗号化|デバイス上のデータ ストレージの暗号化|必須|Select|
|デバイス のセキュリティ|ファイアウォール|必須|Select|
||ウイルス対策|必須|Select|
||スパイウェア対策|必須|Select <p> この設定では、Windows セキュリティ センターに登録されたスパイウェア対策ソリューションが必要です。|
|Defender|Microsoft Defender マルウェア対策|必須|Select|
||Microsoft Defender マルウェア対策の最小バージョン||型 <p> Windows 10 デスクトップでのみサポートされます。 Microsoft では、最新バージョンから 5 つ以上の遅れがないバージョンをお勧めします。|
||Microsoft Defender マルウェア対策のシグネチャを最新の情報に更新|必須|Select|
||リアルタイム保護|必須|Select <p> Windows 10 デスクトップでのみサポート|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

|型|[プロパティ]|値|Action|
|---|---|---|---|
|エンドポイント向け Microsoft Defender の規則|デバイスがコンピューターリスク スコア以下である必要がある|中|Select|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>準拠している PC が必要 (ただし、準拠していない電話やタブレット)

準拠している PC を必要とするポリシーを追加する前に、管理用のデバイスを Intune に登録してください。 デバイスが意図したユーザーを所有することを保証するには、Intune にデバイスを登録する前に多要素認証を使用することを推奨します。

準拠している PC を必要とするには、

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。
2. Azure サービスの一覧で、Azure **Active Directory を選択します**。
3. [管理] **ボックスの** 一覧で、[ **セキュリティ] を** 選択し、[条件付きアクセス] **を選択します**。
4. [ **新しいポリシー] を** 選択し、新しいポリシーの名前を入力します。

5. [ **割り当て**] で [ **ユーザーとグループ] を選択** し、ポリシーを適用するユーザーを含める。 条件付きアクセスの除外グループも除外します。

6. [ **割り当て**] で、[クラウド アプリ **またはアクション] を選択します**。

7. [ **含める**] で、[アプリの選択 **>選択**] を選択し、クラウド アプリの一覧から目的のアプリ **を選択** します。 たとえば、[Exchange Online] を選択します。 完了したら **、[選択** ] を選択します。

8. 準拠している PC (ただし、準拠していない電話やタブレット)を要求するには、[割り当て] で、[デバイス プラットフォームの>**を選択します**。 [構成 **] で [はい** ] を **選択します**。 Choose  **Select device platforms,** select **Windows** and **macOS,** and then choose **Done**.

9. [ **アクセス制御] で、[** 許可] を **選択します** 。

10. Choose **Grant access** and then check Require device to be marked as **compliant**. 複数のコントロールの場合は、[ **選択したコントロールすべてが必要] を選択します**。 完了したら、[選択] を **選択します**。

11. ポリシー **を有効にする場合** は [ **オン] を** 選択し、[作成] を **選択します**。

> [!NOTE]
> このポリシーを有効にする前に、デバイスが準拠している必要があります。 そうしないと、ロックアウトされ、ユーザー アカウントが条件付きアクセスの除外グループに追加されるまで、このポリシーを変更できません。

## <a name="require-compliant-pcs-and-mobile-devices"></a>準拠した PC とモバイル *デバイスが* 必要

すべてのデバイスのコンプライアンスを要求するには:

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。
2. Azure サービスの一覧で、Azure **Active Directory を選択します**。
3. [管理] **ボックスの** 一覧で、[ **セキュリティ] を** 選択し、[条件付きアクセス] **を選択します**。
4. [ **新しいポリシー] を** 選択し、新しいポリシーの名前を入力します。

5. [ **割り当て**] で [ **ユーザーとグループ] を選択** し、ポリシーを適用するユーザーを含める。 条件付きアクセスの除外グループも除外します。

6. [ **割り当て**] で、[クラウド アプリ **またはアクション] を選択します**。

7. [ **含める**] で、[アプリの選択 **>選択**] を選択し、クラウド アプリの一覧から目的のアプリ **を選択** します。 たとえば、[Exchange Online] を選択します。 完了したら **、[選択** ] を選択します。

8. [ **アクセス制御] で、[** 許可] を **選択します** 。

9. Choose **Grant access** and then check Require device to be marked as **compliant**. 複数のコントロールの場合は、[ **選択したコントロールすべてが必要] を選択します**。 完了したら、[選択] を **選択します**。

10. ポリシー **を有効にする場合** は [ **オン] を** 選択し、[作成] を **選択します**。

> [!NOTE]
> このポリシーを有効にする前に、デバイスが準拠している必要があります。 そうしないと、ロックアウトされ、ユーザー アカウントが条件付きアクセスの除外グループに追加されるまで、このポリシーを変更できません。

## <a name="next-step"></a>次の手順

[![手順 3: ゲスト ユーザーと外部ユーザーのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[ゲストユーザーと外部ユーザーに対するポリシーの推奨事項について](identity-access-policies-guest-access.md)
