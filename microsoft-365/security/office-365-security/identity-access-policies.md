---
title: 一般的なゼロ トラスト ID ポリシーとデバイス アクセス ポリシー - Microsoft 365 for enterprise |Microsoft Docs
description: 推奨される一般的なゼロ トラスト ID とデバイス のアクセス ポリシーと構成について説明します。
ms.author: dansimp
author: dansimp
manager: dansimp
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
- zerotrust-solution
ms.technology: mdo
ms.openlocfilehash: 35acb32c9a27ec32c78f4f247257d589a9fefc04
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66750058"
---
# <a name="common-zero-trust-identity-and-device-access-policies"></a>一般的なゼロ トラスト ID ポリシーとデバイス アクセス ポリシー

この記事では、Azure Active Directory (Azure AD) アプリケーション プロキシで公開されたオンプレミス アプリケーションを含め、Microsoft 365 クラウド サービスへのアクセスをセキュリティで保護するための一般的な推奨されるゼロ トラスト ID とデバイス アクセス ポリシーについて説明します。

このガイダンスでは、新しくプロビジョニングされた環境に推奨されるポリシーをデプロイする方法について説明します。 これらのポリシーを別のラボ環境に設定すると、運用前および運用環境へのロールアウトをステージングする前に、推奨されるポリシーを理解し、評価することができます。 新しくプロビジョニングされた環境は、評価のニーズを反映するためにクラウド専用またはハイブリッドにすることができます。

## <a name="policy-set"></a>ポリシー セット

次の図は、推奨される一連のポリシーを示しています。 各ポリシーが適用される保護のレベルと、ポリシーが PC またはスマートフォンおよびタブレットに適用されるか、またはデバイスの両方のカテゴリに適用されるかが示されます。 また、これらのポリシーを構成する場所も示します。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png" alt-text="ゼロ トラスト ID とデバイス アクセスを構成するための一般的なポリシー。" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png":::

<!--

Here's a one-page PDF summary:

[![Thumb image for the Zero Trust identity and device protection for Microsoft 365 handout.](../../media/microsoft-365-policies-configurations/zero-trust-id-device-protection-model-handout-thumbnail.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [View as a PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Download as a PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

-->

この記事の残りの部分では、これらのポリシーを構成する方法について説明します。

> [!NOTE]
> デバイスが目的のユーザーを所有していることを保証するために、デバイスをIntuneに登録する前に、多要素認証 (MFA) の使用を要求することをお勧めします。 デバイス コンプライアンス ポリシーを適用する前に、デバイスをIntuneに登録する必要があります。

これらのタスクを実行する時間を確保するために、この表に示す順序で開始点ポリシーを実装することをお勧めします。 ただし、エンタープライズおよび特殊なセキュリティ レベルの保護に対する MFA ポリシーはいつでも実装できます。

|保護レベル|ポリシー|詳細情報|ライセンス|
|---|---|---|---|
|**開始点**|[サインインのリスクが *中*、または *高* のときに MFA を要求する](#require-mfa-based-on-sign-in-risk)||E5 セキュリティ アドオンを使用したMicrosoft 365 E5またはMicrosoft 365 E3|
||[先進認証をサポートしないクライアントはブロックする](#block-clients-that-dont-support-multi-factor)|先進認証を使用しないクライアントは条件付きアクセス ポリシーをバイパスできるため、これらをブロックすることが重要です。|Microsoft 365 E3 または E5|
||[高リスク ユーザーはパスワードを変更する必要がある](#high-risk-users-must-change-password)|アカウントのリスクの高いアクティビティが検出された場合、サインイン時にユーザーにパスワードの変更を強制します。|E5 セキュリティ アドオンを使用したMicrosoft 365 E5またはMicrosoft 365 E3|
||[アプリケーション保護ポリシー (APP) データ保護の適用](#apply-app-data-protection-policies)|プラットフォーム (Windows iOS/iPadOS、Android) ごとに 1 つの Intune アプリ保護ポリシー。|Microsoft 365 E3 または E5|
||[承認されたアプリとアプリ保護を要求する](#require-approved-apps-and-app-protection)|iOS、iPadOS、Android を使用してスマートフォンやタブレットにモバイル アプリ保護を適用します。|Microsoft 365 E3 または E5|
|**エンタープライズ**|[サインイン リスクが *低* い、*中*、または *高い* 場合に MFA を要求する](#require-mfa-based-on-sign-in-risk)||E5 セキュリティ アドオンを使用したMicrosoft 365 E5またはMicrosoft 365 E3|
||[デバイス コンプライアンス ポリシーを定義する](#define-device-compliance-policies)|プラットフォームごとに 1 つのポリシー。|Microsoft 365 E3 または E5|
||[準拠した PC とモバイル デバイスが必要](#require-compliant-pcs-and-mobile-devices)|PC (Windows または macOS) とスマートフォンまたはタブレット (iOS、iPadOS、または Android) の両方に対してIntune管理を適用します。|Microsoft 365 E3 または E5|
|**特殊なセキュリティ**|[*常に* MFA が必要](#assigning-policies-to-groups-and-users)||Microsoft 365 E3 または E5|

## <a name="assigning-policies-to-groups-and-users"></a>グループとユーザーへのポリシーの割り当て

ポリシーを構成する前に、保護レベルごとに使用している Azure AD グループを特定します。 通常、開始点の保護は組織内のすべてのユーザーに適用されます。 開始点とエンタープライズ保護の両方に含まれるユーザーには、すべての開始点ポリシーとエンタープライズ ポリシーが適用されます。 保護は累積的であり、最も制限の厳しいポリシーが適用されます。

条件付きアクセスの除外用に Azure AD グループを作成することをお勧めします。 [**割り当て]** セクションの [ユーザーとグループの **除外**] 設定で、すべての条件付きアクセス ポリシーに **このグループ** を追加します。 これにより、アクセスの問題のトラブルシューティング中にユーザーにアクセスを提供する方法が提供されます。 これは、一時的なソリューションとしてのみ推奨されます。 このグループの変更を監視し、除外グループが意図したとおりにのみ使用されていることを確認します。

MFA を要求するためのグループの割り当てと除外の例を次に示します。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png" alt-text="MFA ポリシーのグループの割り当てと除外の例" lightbox="../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png":::

結果は次のとおりです。

- サインイン リスクが中程度または高い場合は、すべてのユーザーが MFA を使用する必要があります。

- サインイン リスクが低い、中、または高い場合、エグゼクティブ スタッフ グループのメンバーは MFA を使用する必要があります。

  この場合、Executive Staff グループのメンバーは、開始点ポリシーとエンタープライズ条件付きアクセス ポリシーの両方に一致します。 両方のポリシーのアクセス制御が組み合わされます。この場合、エンタープライズ条件付きアクセス ポリシーと同じです。

- MFA を使用するには、常にトップ シークレット プロジェクト X グループのメンバーが必要です

  この場合、トップ シークレット プロジェクト X グループのメンバーは、開始点と特殊なセキュリティ条件付きアクセス ポリシーの両方に一致します。 両方のポリシーのアクセス制御が組み合わされます。 特殊なセキュリティ条件付きアクセス ポリシーのアクセス制御の方が制限が厳しいため、使用されます。

より高いレベルの保護をグループとユーザーに適用する場合は注意してください。 たとえば、トップ シークレット プロジェクト X グループのメンバーは、Project X の特殊なセキュリティ コンテンツで作業していない場合でも、サインインするたびに MFA を使用する必要があります。

これらの推奨事項の一部として作成されたすべての Azure AD グループは、Microsoft 365 グループとして作成する必要があります。 これは、Microsoft Teams と SharePoint でドキュメントをセキュリティで保護する際に機密ラベルを展開する場合に重要です。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png" alt-text="Microsoft 365 グループの作成" lightbox="../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png":::

## <a name="require-mfa-based-on-sign-in-risk"></a>サインイン リスクに基づいて MFA を要求する

使用を要求する前に、ユーザーに MFA の登録を求める必要があります。 E5 セキュリティ アドオン、EMS E5 を使用したOffice 365、または個々のAzure AD Premium P2 ライセンスでMicrosoft 365 E5、Microsoft 365 E3している場合は、Azure AD Identity Protection で MFA 登録ポリシーを使用して、ユーザーに MFA の登録を要求できます。 [前提条件の作業](identity-access-prerequisites.md)には、すべてのユーザーを MFA に登録する必要があります。

ユーザーが登録されたら、新しい条件付きアクセス ポリシーを使用してサインインするために MFA を要求できます。

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。
2. Azure サービスの一覧で、 **Azure Active Directory** を選択します。
3. [ **管理** ] ボックスの一覧で [ **セキュリティ**] を選択し、[ **条件付きアクセス**] を選択します。
4. [ **新しいポリシー]** を選択し、新しいポリシーの名前を入力します。

次の表では、サインイン リスクに基づいて MFA を要求する条件付きアクセス ポリシー設定について説明します。

[ **割り当て] セクションで、次の手順を実行** します。

|Setting|[プロパティ]|値|注|
|---|---|---|---|
|ユーザーとグループ|含める|**[ユーザーとグループ] >ユーザーとグループ** を選択する: 対象のユーザー アカウントを含む特定のグループを選択します。|パイロット ユーザー アカウントを含むグループから始めます。|
||除外|**ユーザーとグループ**: 条件付きアクセス例外グループを選択します。サービス アカウント (アプリ ID)。|メンバーシップは、必要に応じて一時的に変更する必要があります。|
|クラウド アプリまたはアクション|**クラウド アプリ>含める**|**アプリの選択**: このポリシーを適用するアプリを選択します。 たとえば、Exchange Onlineを選択します。||
|条件|||環境とニーズに固有の条件を構成します。|
||サインイン リスク||次の表のガイダンスを参照してください。|

### <a name="sign-in-risk-condition-settings"></a>サインイン リスク条件の設定

ターゲットとする保護レベルに基づいて、リスク レベルの設定を適用します。

|保護レベル|必要なリスク レベルの値|アクション|
|---|---|---|
|開始点|高、中|両方を確認します。|
|大規模企業|高、中、低|3 つすべてを確認します。|
|特殊なセキュリティ||MFA を常に適用するには、すべてのオプションをオフのままにします。|

[ **アクセス制御** ] セクションで、次の操作を行います。

|Setting|[プロパティ]|値|アクション|
|---|---|---|---|
|許可|**Grant access**||選択|
|||**多要素認証を要求する**|チェック|
||**選択したコントロールすべてが必要**||選択|

[ **選択] を選択** して **、[許可]** 設定を保存します。

最後に、[**ポリシーを有効にする**] **で [オン**] を選択し、[**作成**] を選択します。

また、 [What if](/azure/active-directory/active-directory-conditional-access-whatif) ツールを使用してポリシーをテストすることも検討してください。

## <a name="block-clients-that-dont-support-multi-factor"></a>多要素をサポートしていないクライアントをブロックする

条件付きアクセス ポリシーのこれらのテーブルの設定を使用して、多要素認証をサポートしていないクライアントをブロックします。

多要素認証をサポートする Microsoft 365 のクライアントの一覧については、 [この記事](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) を参照してください。

[ **割り当て] セクションで、次の手順を実行** します。

|Setting|[プロパティ]|値|注|
|---|---|---|---|
|ユーザーとグループ|含める|**[ユーザーとグループ] >ユーザーとグループ** を選択する: 対象のユーザー アカウントを含む特定のグループを選択します。|パイロット ユーザー アカウントを含むグループから始めます。|
||除外|**ユーザーとグループ**: 条件付きアクセス例外グループを選択します。サービス アカウント (アプリ ID)。|メンバーシップは、必要に応じて一時的に変更する必要があります。|
|クラウド アプリまたはアクション|**クラウド アプリ>含める**|**アプリの選択**: 最新の認証をサポートしていないクライアントに対応するアプリを選択します。||
|条件|**クライアント アプリ**|**[構成**] **で [はい**] を選択する <p> **ブラウザー** と **モバイル のアプリとデスクトップ クライアント** のチェック マークをオフにする||

[ **アクセス制御** ] セクションで、次の操作を行います。

|Setting|[プロパティ]|値|アクション|
|---|---|---|---|
|許可|**[アクセスのブロック]**||選択|
||**選択したコントロールすべてが必要**||選択|

[ **選択] を選択** して **、[許可]** 設定を保存します。

最後に、[**ポリシーを有効にする**] **で [オン**] を選択し、[**作成**] を選択します。

[What if](/azure/active-directory/active-directory-conditional-access-whatif) ツールを使用してポリシーをテストすることを検討してください。

Exchange Onlineでは、認証ポリシーを使用して [Basic 認証を無効に](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)できます。これにより、すべてのクライアント アクセス要求で先進認証が強制的に使用されます。

## <a name="high-risk-users-must-change-password"></a>高リスク ユーザーはパスワードを変更する必要がある

サインイン時に、危険度の高いユーザーの侵害されたアカウントがすべてパスワード変更を強制されるようにするには、次のポリシーを適用する必要があります。

管理者資格情報を使用して [Microsoft Azure ポータル (https://portal.azure.com)](https://portal.azure.com/) にログインしてから、**[Azure AD Identity Protection]、[ユーザーのリスク ポリシー]** の順に移動します。

[ **割り当て] セクションで、次の手順を実行** します。

|型|[プロパティ]|値|アクション|
|---|---|---|---|
|Users|含める|**すべてのユーザー**|選択|
|ユーザーのリスク|**High**||選択|

2 番目の **[割り当て] セクションで、次の操作を行います** 。

|型|[プロパティ]|値|アクション|
|---|---|---|---|
|Access|**SSL 経由でのみ**||選択|
|||**パスワードの変更を必須とする**|チェック|

[ **完了] を** 選択して **、アクセス** 設定を保存します。

最後に、[**ポリシーの適用****] で [オン**] を選択し、[**保存]** を選択します。

[What if](/azure/active-directory/active-directory-conditional-access-whatif) ツールを使用してポリシーをテストすることを検討してください。

このポリシーは、組織に固有の既知の脆弱なパスワードとそのバリアントや追加の脆弱な用語を検出してブロックする [Azure AD パスワード保護の構成](/azure/active-directory/authentication/concept-password-ban-bad)と組み合わせて使用します。 Azure AD パスワード保護を使用すると、変更されたパスワードが強力なパスワードになります。

## <a name="apply-app-data-protection-policies"></a>アプリ データ保護ポリシーを適用する

APPS では、許可されるアプリと、組織のデータに対して実行できるアクションが定義されます。 APP で使用できる選択肢により、組織は特定のニーズに合わせて保護を調整できます。 場合によっては、完全なシナリオを実装するためにどのポリシー設定が必要であるかが明確ではないことがあります。 組織がモバイル クライアント エンドポイントのセキュリティ強化を優先できるよう、Microsoft では、iOS および Android モバイル アプリ管理のための APP データ保護フレームワークの分類を導入しました。

APP データ保護フレームワークは 3 つの異なる構成レベルに編成されており、各レベルは前のレベルを基に構築されています。

- **レベル 1: エンタープライズ基本データ保護** により、アプリが PIN で保護され、暗号化され、選択的ワイプ操作が実行されます。 Android デバイスの場合、このレベルでは Android デバイスの構成証明を検証します。 これは、Exchange Online メールボックス ポリシーに類似したデータ保護制御を提供し、IT 部門およびユーザー集団に APP を経験させる、エントリ レベルの構成です。
- **レベル 2: エンタープライズ強化されたデータ保護により** 、APP データ漏えい防止メカニズムと最小 OS 要件が導入されます。 この構成は、職場または学校のデータにアクセスするほとんどのモバイル ユーザーに適用されます。
- **レベル 3: エンタープライズ高データ保護** では、高度なデータ保護メカニズム、強化された PIN 構成、APP Mobile Threat Defense が導入されています。 この構成は、危険度の高いデータにアクセスするユーザーに適しています。

各構成レベルおよび、最低限保護する必要のあるアプリに関する具体的な推奨事項については、「[アプリ保護ポリシーを使用するデータ保護フレームワーク](/mem/intune/apps/app-protection-framework)」を参照してください。

[ゼロ トラスト ID とデバイス アクセスの構成](microsoft-365-policies-configurations.md)で説明されている原則を使用して、開始点とエンタープライズの保護レベルは、レベル 2 のエンタープライズ拡張データ保護設定と密接にマップされます。 特殊セキュリティ保護レベルは、レベル 3 エンタープライズの高データ保護設定に密接に対応します。

|保護レベル|アプリ保護ポリシー|詳細情報|
|---|---|---|
|開始点|[レベル 2 の強化されたデータ保護](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|レベル 2 に適用されるポリシー設定には、レベル 1 に推奨されるすべてのポリシー設定が含まれ、レベル 1 よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定にのみ追加または更新されます。|
|大規模企業|[レベル 2 の強化されたデータ保護](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|レベル 2 に適用されるポリシー設定には、レベル 1 に推奨されるすべてのポリシー設定が含まれ、レベル 1 よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定にのみ追加または更新されます。|
|特殊なセキュリティ|[レベル 3 エンタープライズの高データ保護](/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|レベル 3 に適用されるポリシー設定には、レベル 1 とレベル 2 に推奨されるすべてのポリシー設定が含まれており、レベル 2 よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定にのみ追加または更新されます。|

データ保護フレームワークの設定を使用して、Microsoft エンドポイント マネージャー内のプラットフォーム (iOS および Android) ごとに新しいアプリ保護ポリシーを作成するには、次の操作を行います。

1. Microsoft Intuneを使用して[アプリ保護ポリシーを作成して展開する方法に関する手順に従って、ポリシーを手動で作成](/mem/intune/apps/app-protection-policies)します。
2. [Intuneの PowerShell スクリプト](https://github.com/microsoftgraph/powershell-intune-samples)[を使用して、App Protection Policy Configuration Framework JSON テンプレート](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies)Intuneサンプルをインポートします。

## <a name="require-approved-apps-and-app-protection"></a>承認されたアプリと APP 保護を要求する

Intuneに適用したアプリ保護 ポリシーを適用するには、承認済みのクライアント アプリと APP 保護ポリシーに設定された条件を要求する条件付きアクセス ポリシーを作成する必要があります。

アプリ保護 ポリシーを適用するには、「[条件付きアクセスを使用してクラウド アプリへのアクセスにアプリ保護ポリシーを要求する」](/azure/active-directory/conditional-access/app-protection-based-conditional-access)で説明されている一連のポリシーが必要です。 これらのポリシーは、それぞれ、この推奨される ID およびアクセス構成ポリシーのセットに含まれています。

承認済みのアプリと APP 保護を必要とする条件付きアクセス ポリシーを作成するには、「[モバイル デバイスで承認済みのクライアント アプリまたはアプリ保護ポリシーを要求する」](/azure/active-directory/conditional-access/howto-policy-approved-app-or-app-protection#require-approved-client-apps-or-app-protection-policy-with-mobile-devices)の手順に従います。このポリシーでは、アプリ保護 ポリシーで保護されているモバイル アプリ内のアカウントのみが Microsoft 365 エンドポイントにアクセスできます。

   > [!NOTE]
   > このポリシーにより、モバイル ユーザーは該当するアプリを使用して、すべての Microsoft 365 エンドポイントにアクセスできるようになります。

また、このポリシーにより、モバイル デバイス上のExchange ActiveSync クライアントが Exchange Online に接続できなくなります。 ただし、すべてのデバイスでExchange ActiveSyncを処理するための別のポリシーを作成できます。 詳細については、「[ActiveSync クライアントをブロック](secure-email-recommended-policies.md#block-activesync-clients)する」を参照してください。これにより、基本認証を利用するクライアントExchange ActiveSync Exchange Onlineに接続できなくなります。 このポリシーは、この記事の上部の図には示されていません。 電子 [メールのセキュリティ保護に関するポリシーの推奨事項](secure-email-recommended-policies.md)に関する説明と図を示します。

 このポリシーでは、承認 [されたクライアント アプリとアプリ保護ポリシーを必要とする](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) 許可コントロール [を利用します](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)。

最後に、iOS および Android デバイス上の他のクライアント アプリのレガシ認証をブロックすると、これらのクライアントが条件付きアクセス ポリシーをバイパスできなくなります。 この記事のガイダンスに従っている場合は、 [最新の認証をサポートしていないブロック クライアント](#block-clients-that-dont-support-multi-factor)を既に構成しています。

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>デバイス コンプライアンス ポリシーを定義する

デバイスコンプライアンス ポリシーは、デバイスが準拠として決定するために満たす必要がある要件を定義します。 Intuneデバイス コンプライアンス ポリシーは、Microsoft エンドポイント マネージャー管理センター内から作成します。

PC、スマートフォン、またはタブレット プラットフォームごとにポリシーを作成する必要があります。

- Android デバイス管理者
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 以降
- Windows 10 以降

デバイス コンプライアンス ポリシーを作成するには、管理者の資格情報を使用して [Microsoft エンドポイント マネージャー 管理 センター](https://endpoint.microsoft.com)にログインし、**デバイス** \> **コンプライアンス ポリシー** \> **ポリシー** に移動します。 **[ポリシーを作成する]** を選択します。

デバイス コンプライアンス ポリシーを展開するには、ユーザー グループに割り当てる必要があります。 ポリシーは、作成して保存した後に割り当てます。 管理センターでポリシーを選択し、[ **割り当て**] を選択します。 ポリシーを受け取るグループを選択したら、[ **保存]** を選択してそのグループの割り当てを保存し、ポリシーを展開します。

Intuneでのコンプライアンス ポリシーの作成に関する詳細なガイダンスについては、Intune のドキュメント[の「Microsoft Intuneでのコンプライアンス ポリシーの作成](/mem/intune/protect/create-compliance-policy)」を参照してください。

### <a name="recommended-settings-for-ios"></a>iOS の推奨設定

iOS/iPadOS ではいくつかの登録シナリオがサポートされていますが、そのうち 2 つはこのフレームワークの一部として扱われています。

- [個人所有のデバイスのデバイス登録](/mem/intune/enrollment/ios-enroll) – これらのデバイスは個人所有であり、職場と個人の両方の使用に使用されます。
- [企業所有のデバイスの監視付き自動デバイス登録](/mem/intune/enrollment/device-enrollment-program-enroll-ios) – これらのデバイスは、企業所有であり、1 人のユーザーに関連付け、個人の使用ではなく、仕事専用に使用されます。

iOS/iPadOS セキュリティ構成フレームワークは、いくつかの異なる構成シナリオに編成され、個人所有および監視対象のデバイスに関するガイダンスを提供します。

個人所有のデバイスの場合:

- 基本的なセキュリティ (レベル 1) – Microsoft では、ユーザーが職場または学校のデータにアクセスする個人用デバイスの最小セキュリティ構成として、この構成をお勧めします。 これを行うには、パスワード ポリシー、デバイス ロック特性を適用し、特定のデバイス機能 (信頼できない証明書など) を無効にします。
- セキュリティの強化 (レベル 2) - ユーザーが機密情報や機密情報にアクセスするデバイスに対して、この構成をお勧めします。 この構成では、データ共有の統制を適用します。 この構成は、デバイス上の職場や学校のデータにアクセスするほとんどのモバイル ユーザーに適用されます。
- 高いセキュリティ (レベル 3) – Microsoft では、一意のリスクが高い特定のユーザーまたはグループ (承認されていない開示によって組織に重大な重大な損失が発生する機密性の高いデータを処理するユーザー) によって使用されるデバイスに対して、この構成をお勧めします。 この構成により、より強力なパスワード ポリシーが適用され、特定のデバイス機能が無効になり、追加のデータ転送制限が適用されます。

監視対象デバイスの場合:

- 基本的なセキュリティ (レベル 1) – Microsoft では、ユーザーが職場または学校のデータにアクセスする監視対象デバイスの最小セキュリティ構成として、この構成をお勧めします。 これを行うには、パスワード ポリシー、デバイス ロック特性を適用し、特定のデバイス機能 (信頼できない証明書など) を無効にします。
- セキュリティの強化 (レベル 2) - ユーザーが機密情報や機密情報にアクセスするデバイスに対して、この構成をお勧めします。 この構成では、データ共有の統制を適用し、USB デバイスへのアクセスをブロックします。 この構成は、デバイス上の職場や学校のデータにアクセスするほとんどのモバイル ユーザーに適用されます。
- 高いセキュリティ (レベル 3) – Microsoft では、一意のリスクが高い特定のユーザーまたはグループ (承認されていない開示によって組織に重大な重大な損失が発生する機密性の高いデータを処理するユーザー) によって使用されるデバイスに対して、この構成をお勧めします。 この構成では、より強力なパスワード ポリシーが適用され、特定のデバイス機能が無効になり、追加のデータ転送制限が適用され、Apple のボリューム購入プログラムを通じてアプリをインストールする必要があります。

[ゼロ トラスト ID とデバイス アクセスの構成](microsoft-365-policies-configurations.md)で説明されている原則を使用して、開始点層と Enterprise 保護レベルは、レベル 2 の強化されたセキュリティ設定と密接にマップされます。 特殊セキュリティ保護レベルは、レベル 3 の高いセキュリティ設定に密接にマップされます。

|保護レベル  |デバイス ポリシー |詳細情報  |
|---------|---------|---------|
|開始点     |強化されたセキュリティ (レベル 2)         |レベル 2 に適用されるポリシー設定には、レベル 1 に推奨されるすべてのポリシー設定が含まれ、レベル 1 よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定にのみ追加または更新されます。         |
|大規模企業     |強化されたセキュリティ (レベル 2)         |レベル 2 に適用されるポリシー設定には、レベル 1 に推奨されるすべてのポリシー設定が含まれ、レベル 1 よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定にのみ追加または更新されます。         |
|特殊なセキュリティ     |高セキュリティ (レベル 3)         |レベル 3 に適用されるポリシー設定には、レベル 1 とレベル 2 に推奨されるすべてのポリシー設定が含まれており、レベル 2 よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定にのみ追加または更新されます。         |

各構成レベルの特定のデバイス コンプライアンスとデバイス制限の推奨事項を確認するには、 [iOS/iPadOS セキュリティ構成フレームワークを確認します](/mem/intune/enrollment/ios-ipados-configuration-framework)。

### <a name="recommended-settings-for-android"></a>Android の推奨設定

Android Enterprise では、いくつかの登録シナリオがサポートされています。そのうちの 2 つは、このフレームワークの一部として説明されています。

- [Android Enterprise の仕事用プロファイル](/intune/android-work-profile-enroll) – 通常、この登録モデルは個人所有のデバイスに使用されます。IT 担当者は、仕事と個人のデータの間に明確な分離境界を提供したいと考えています。 IT によって制御されるポリシーにより、仕事用データを個人プロファイルに転送できなくなります。
- [Android Enterprise のフル マネージド デバイス](/intune/android-fully-managed-enroll) – これらのデバイスは企業所有であり、1 人のユーザーに関連付け、個人の使用ではなく、仕事専用で使用されます。

Android Enterprise セキュリティ構成フレームワークは、いくつかの異なる構成シナリオに編成され、作業プロファイルと完全に管理されたシナリオのガイダンスを提供します。

Android Enterprise 仕事用プロファイル デバイスの場合:

- 仕事用プロファイルの強化されたセキュリティ (レベル 2) - Microsoft では、ユーザーが職場または学校のデータにアクセスする個人用デバイスの最小セキュリティ構成として、この構成をお勧めします。 この構成では、パスワード要件が導入され、仕事用のデータと個人データが分離され、Android デバイスの構成証明が検証されます。
- 仕事用プロファイルの高いセキュリティ (レベル 3) – Microsoft では、一意のリスクが高い特定のユーザーまたはグループ (承認されていない開示によって組織に重大な重大な損失が発生する機密性の高いデータを処理するユーザー) によって使用されるデバイスに対して、この構成をお勧めします。 この構成では、モバイル脅威の防御またはMicrosoft Defender for Endpointが導入され、Android の最小バージョンが設定され、より強力なパスワード ポリシーが適用され、作業と個人の分離がさらに制限されます。

Android Enterprise のフル マネージド デバイスの場合:

- 完全に管理された基本的なセキュリティ (レベル 1) – Microsoft では、エンタープライズ デバイスの最小セキュリティ構成としてこの構成をお勧めします。 この構成は、職場または学校のデータにアクセスするほとんどのモバイル ユーザーに適用されます。 この構成では、パスワード要件が導入され、Android の最小バージョンが設定され、特定のデバイス制限が適用されます。
- フル マネージドの強化されたセキュリティ (レベル 2) - ユーザーが機密情報や機密情報にアクセスするデバイスに対して、この構成をお勧めします。 この構成により、より強力なパスワード ポリシーが適用され、ユーザー/アカウントの機能が無効になります。
- 完全に管理された高セキュリティ (レベル 3) - Microsoft では、一意のリスクが高い特定のユーザーまたはグループ (承認されていない開示によって組織に重大な重大な損失が発生する機密性の高いデータを処理するユーザー) によって使用されるデバイスに対して、この構成をお勧めします。 この構成により、Android の最小バージョンが増加し、モバイル脅威の防御やMicrosoft Defender for Endpointが導入され、追加のデバイス制限が適用されます。

[ゼロ トラスト ID とデバイスのアクセス構成](microsoft-365-policies-configurations.md)で説明されている原則を使用して、開始点とエンタープライズ保護レベルは、個人所有のデバイスのレベル 1 の基本的なセキュリティと、フル マネージド デバイスのレベル 2 の強化されたセキュリティ設定と密接に対応します。 特殊セキュリティ保護レベルは、レベル 3 の高いセキュリティ設定に密接にマップされます。

Android Enterprise 仕事用プロファイル デバイスの場合:

|保護レベル  |デバイス ポリシー |詳細情報  |
|---------|---------|---------|
|開始点     |作業プロファイル: 基本的なセキュリティ (レベル 1)      |該当なし         |
|大規模企業     |作業プロファイル: 基本的なセキュリティ (レベル 1)         |該当なし         |
|開始点     |フル マネージド: 強化されたセキュリティ (レベル 2)       |レベル 2 に適用されるポリシー設定には、レベル 1 に推奨されるすべてのポリシー設定が含まれ、レベル 1 よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定にのみ追加または更新されます。         |
|大規模企業     |フル マネージド: 強化されたセキュリティ (レベル 2)         |レベル 2 に適用されるポリシー設定には、レベル 1 に推奨されるすべてのポリシー設定が含まれ、レベル 1 よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定にのみ追加または更新されます。         |
|特殊なセキュリティ     |高セキュリティ (レベル 3)         |レベル 3 に適用されるポリシー設定には、レベル 1 とレベル 2 に推奨されるすべてのポリシー設定が含まれており、レベル 2 よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定にのみ追加または更新されます。         |

各構成レベルの特定のデバイス コンプライアンスとデバイス制限の推奨事項を確認するには、 [Android Enterprise Security Configuration Framework を確認します](/mem/intune/enrollment/android-configuration-framework)。

### <a name="recommended-settings-for-windows-10-and-later"></a>Windows 10以降の推奨設定

ポリシー作成プロセスの **手順 2: コンプライアンス** 設定で構成されているように、Windows 10 以降を実行している PC には、次の設定をお勧めします。

**デバイス正常性> Windows Health 構成証明サービスの評価規則** については、次の表を参照してください。

|プロパティ|値|アクション|
|---|---|---|
|BitLocker が必要|必須|選択|
|デバイスでセキュア ブートを有効にする必要がある|必須|選択|
|コードの整合性を要求する|必須|選択|

**[デバイスのプロパティ]** で、IT ポリシーとセキュリティ ポリシーに基づいてオペレーティング システムのバージョンに適切な値を指定します。

**[Configuration Managerコンプライアンス**] で、[**必須**] を選択します。

**システム セキュリティ** については、次の表を参照してください。

|型|[プロパティ]|値|アクション|
|---|---|---|---|
|Password|モバイル デバイスのロックを解除するパスワードを要求する|必須|選択|
||単純なパスワード|ブロック|選択|
||パスワードの種類|デバイスの既定値|選択|
||パスワードの最小文字数|6 |型|
||パスワードが要求されるまでの非アクティブの最長時間 (分)|15|型 <p> この設定は、Android バージョン 4.0 以降または KNOX 4.0 以降でサポートされています。 iOS デバイスの場合は、iOS 8.0 以降でサポートされています。|
||パスワードの有効期限 (日)|41|型|
||再使用を禁止するパスワード世代数|5|型|
||デバイスがアイドル状態から戻ったときにパスワードを要求する (モバイルとホログラフィック)|必須|Windows 10以降で使用できます|
|暗号化|デバイス上のデータ ストレージの暗号化|必須|選択|
|デバイス セキュリティ|ファイアウォール|必須|選択|
||ウイルス対策|必須|選択|
||スパイウェア対策|必須|選択 <p> この設定には、Windows セキュリティ アプリに登録されたスパイウェア対策ソリューションが必要です。|
|Defender for Cloud|Microsoft Defender マルウェア対策|必須|選択|
||Microsoft Defender マルウェア対策の最小バージョン||型 <p> Windows 10 デスクトップでのみサポートされます。 Microsoft では、最新バージョンから 5 つ以下のバージョンをお勧めします。|
||最新の Microsoft Defender マルウェア対策シグネチャ|必須|選択|
||リアルタイム保護|必須|選択 <p> Windows 10以降のデスクトップでのみサポートされる|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

|型|[プロパティ]|値|アクション|
|---|---|---|---|
|Microsoft エンドポイント マネージャー 管理センターでルールをMicrosoft Defender for Endpointする|[デバイスがマシン リスク スコアの下に存在することを要求する](/mem/intune/protect/advanced-threat-protection-configure#create-and-assign-compliance-policy-to-set-device-risk-level)|中|選択|

<!--
## Require compliant PCs (but not compliant phones and tablets)

Before adding a policy to require compliant PCs, be sure to enroll your devices for management in Intune. Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.

To require compliant PCs:

1. Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.
2. In the list of Azure services, choose **Azure Active Directory**.
3. In the **Manage** list, choose **Security**, and then choose **Conditional Access**.
4. Choose **New policy** and type the new policy's name.

5. Under **Assignments**, choose **Users and groups** and include who you want the policy to apply to. Also exclude your Conditional Access exclusion group.

6. Under **Assignments**, choose **Cloud apps or actions**.

7. For **Include**, choose **Select apps > Select**, and then select the desired apps from the **Cloud apps** list. For example, select Office 365. Choose **Select** when done.

8. To require compliant PCs (but not compliant phones and tablets), under **Assignments**, choose **Conditions > Device platforms**. Select **Yes** for **Configure**. Choose  **Select device platforms**, select **Yes** and select **Any device** and under Exclude select **iOS** and **Android**, and then choose **Done**.

9. Under **Access controls**, choose **Grant** .

10. Choose **Grant access** and then check **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**. When complete, choose **Select**.

11. Select **On** for **Enable policy**, and then choose **Create**.

> [!NOTE]
> Make sure that your device is compliant before enabling this policy. Otherwise, you could get locked out and will be unable to change this policy until your user account has been added to the Conditional Access exclusion group.

-->

## <a name="require-compliant-pcs-and-mobile-devices"></a>準拠した PC とモバイル デバイスが必要

すべてのデバイスに対してコンプライアンスを要求するには:

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。
2. Azure サービスの一覧で、 **Azure Active Directory** を選択します。
3. [ **管理** ] ボックスの一覧で [ **セキュリティ**] を選択し、[ **条件付きアクセス**] を選択します。
4. [ **新しいポリシー]** を選択し、新しいポリシーの名前を入力します。

5. [ **割り当て**] で [ **ユーザーとグループ** ] を選択し、ポリシーを適用するユーザーを含めます。 条件付きアクセス除外グループも除外します。

6. **[割り当て**] で、[**クラウド アプリまたはアクション**] を選択します。

7. [ **含める**] で [ **アプリの選択] > [選択]** を選択し、 **Cloud アプリ** の一覧から目的のアプリを選択します。 たとえば、Office 365を選択します。 [完了時 **に選択] を選択します** 。

8. **[アクセス制御**] で 、[**許可**] を選択します。

9. [ **アクセスの許可]** を選択し、[ **デバイスを準拠としてマークする必要があります**] をオンにします。 複数のコントロールの場合は、[ **選択したすべてのコントロールが必要] を選択します**。 完了したら、[選択] を **選択します**。

10. [ポリシーを **有効にする]** **で [オン**] を選択し、[**作成**] を選択します。

> [!NOTE]
> このポリシーを有効にする前に、デバイスが準拠していることを確認してください。 そうしないと、ロックアウトされ、ユーザー アカウントが条件付きアクセス除外グループに追加されるまで、このポリシーを変更できません。

## <a name="next-step"></a>次のステップ

[![手順 3: ゲストユーザーと外部ユーザーのポリシー。](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png#lightbox)](identity-access-policies-guest-access.md)

[ゲストユーザーと外部ユーザーに対するポリシーの推奨事項について説明します](identity-access-policies-guest-access.md)
