---
title: 一般的な id およびデバイスアクセスポリシー-Microsoft 365 for enterprise |Microsoft Docs
description: ID およびデバイス アクセス ポリシーと構成を適用する方法に関する Microsoft の推奨事項のポリシーを説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
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
ms.openlocfilehash: 699bc04c8e286c004e1f47ae6825ae311434d9cb
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898118"
---
# <a name="common-identity-and-device-access-policies"></a>共通 ID とデバイスのアクセス ポリシー
この記事では、Azure AD Application Proxy で公開されているオンプレミスアプリケーションを含む、クラウドサービスへのアクセスを保護するための一般的な推奨ポリシーについて説明します。 

このガイダンスでは、新しくプロビジョニングされた環境に推奨されるポリシーを展開する方法について説明します。 個別のラボ環境でこれらのポリシーを設定することにより、展開をステージングおよび運用環境にステージングする前に、推奨ポリシーを理解し、評価することができます。 新しくプロビジョニングされた環境は、クラウド専用またはハイブリッドの場合があります。  

## <a name="policy-set"></a>ポリシーセット 

次の図は、推奨されるポリシーセットを示しています。 この図は、各ポリシーが適用される保護層と、それらのポリシーが Pc、電話、タブレット、または両方のカテゴリのデバイスに適用されるかどうかを示しています。 また、これらのポリシーが構成されている場所も示されます。

[ ![ Id とデバイスのアクセスを構成するための一般的なポリシー](../media/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png) 
 [この画像の大規模なバージョンの表示](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png)

この記事の残りの部分では、これらのポリシーを構成する方法について説明します。 

デバイスが目的のユーザーを所有していることを保証するために、デバイスを Intune に登録する前に、多要素認証を使用することをお勧めします。 デバイスコンプライアンスポリシーを適用する前に、デバイスを Intune に登録する必要もあります。

これらのタスクを実行するための時間を提供するために、この表に記載されている順序で基準ポリシーを実装することをお勧めします。 ただし、機密性が高く規制された保護のための MFA ポリシーは、いつでも実装できます。


|保護レベル|ポリシー|詳細|
|:---------------|:-------|:----------------|
|**Baseline**|[サインインリスクが*中*または*高*の場合は MFA を必須にする](#require-mfa-based-on-sign-in-risk)| |
|        |[先進認証をサポートしないクライアントはブロックする](#block-clients-that-dont-support-modern-authentication)|モダン認証を使用していないクライアントは、条件付きアクセスルールをバイパスすることができます。そのため、これらをブロックすることが重要です。|
|        |[高リスク ユーザーはパスワードを変更する必要がある](#high-risk-users-must-change-password)|アカウントに対して高リスクのアクティビティが検出された場合に、サインイン時にユーザーにパスワードを変更することを強制します。|
|        |[アプリデータ保護ポリシーを適用する](#apply-app-data-protection-policies)|プラットフォームごとに1つのポリシー (iOS、Android、Windows)。 Intune App Protection ポリシー (アプリ) は、レベル1からレベル3までの事前に定義された保護のセットです。|
|        |[承認済みアプリとアプリ保護を必要とする](#require-approved-apps-and-app-protection)|携帯電話とタブレットにモバイルアプリの保護を適用する|
|        |[デバイスコンプライアンスポリシーの定義](#define-device-compliance-policies)|プラットフォームごとに1つのポリシー|
|        |[準拠 PC が必要](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Pc の Intune 管理を強制する|
|**機密**|[サインインリスクが*低*、*中*、*高*のときに MFA を必要とする](#require-mfa-based-on-sign-in-risk)| |
|         |[準拠 *して* いる pc とモバイルデバイスが必要](#require-compliant-pcs-and-mobile-devices)|Pc と携帯電話/タブレットに Intune 管理を強制する|
|**厳しく規制**|[*常に* MFA が必要](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>ユーザーへのポリシーの割り当て
ポリシーを構成する前に、各層の保護に使用している Azure AD グループを特定します。 通常、ベースライン保護は組織内の全員に適用されます。 ベースラインと機密保護の両方に含まれているユーザーには、適用されているすべてのベースラインポリシーと、機密ポリシーが適用されます。 保護は累積され、最も制限の厳しいポリシーが適用されます。 

条件付きアクセスの除外に対して Azure AD グループを作成することをお勧めします。 [除外] の下にあるすべての条件付きアクセスルールにこのグループを追加します。 これにより、アクセスの問題のトラブルシューティングを行っている間、ユーザーにアクセス権を与えることができます。 これは、一時的なソリューションとしてのみお勧めします。 このグループを監視して変更を確認し、除外グループが意図したとおりにのみ使用されていることを確認します。 

次の図は、ユーザーの割り当てと除外の例を示しています。

![MFA ルールのユーザー割り当てと除外の例](../media/identity-access-policies-assignment.png)

図では、"Top secret プロジェクト X teams *" には、MFA を*必要とする条件付きアクセスポリシーが割り当てられています。 ユーザーにより高度な保護を適用する場合は、慎重に行います。 このプロジェクトチームのメンバーは、厳しく規制されたコンテンツを表示していない場合でも、ログオンするたびに2つの形式の認証を提供する必要があります。  

これらの推奨事項の一部として作成されたすべての Azure AD グループは、Microsoft 365 グループとして作成する必要があります。 これは、SharePoint Online のドキュメントをセキュリティで保護する場合の Azure Information Protection (AIP) の展開で特に重要です。

![Microsoft 365 グループを作成するための画面キャプチャ](../media/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>サインインリスクに基づいて MFA を必須にする
MFA を必要とする前に、まず Identity Protection MFA 登録ポリシーを使用して、MFA のユーザーを登録します。 ユーザーが登録されたら、サインインに MFA を適用することができます。 [前提条件](identity-access-prerequisites.md)となるのは、すべてのユーザーを MFA で登録することです。

条件付きアクセス ポリシーを作成するには: 

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。 サインインに成功すると、Azure ダッシュボードが表示されます。

2. 左側のメニューから **[Azure Active Directory]** を選びます。

3. **[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。

4. **[新しいポリシー]** を選びます。

![ベースラインとなる CA ポリシー](../media/secure-email/CA-EXO-policy-1.png)

 次の表では、このポリシーに対して実装する条件付きアクセスポリシー設定について説明します。

**Assignments**

|型|[プロパティ]|値|注|
|:---|:---------|:-----|:----|
|ユーザーとグループ|含める|ユーザーとグループの選択 – 対象ユーザーを含む特定のセキュリティ グループを選択します|パイロット ユーザーを含むセキュリティ グループから開始します|
||除外|例外セキュリティ グループ、サービス アカウント (アプリ ID)|必要に応じて変更されたメンバーシップの一時的根拠|
|クラウド アプリ|含める|このルールを適用するアプリを選択します。 たとえば、[Exchange Online] を選択します。||
|条件|構成済み|はい|使用環境およびニーズに合わせて構成します|
|サインイン リスク|リスク レベル||次の表のガイダンスを参照してください。|

**サインイン リスク**

対象とする保護レベルに基づいて設定を適用します。

|プロパティ|保護レベル|値|注|
|:---|:---------|:-----|:----|
|リスク レベル|基準|高、中|両方をチェック|
| |機密|高、中、低|3 つすべてチェック|
| |厳しく規制| |すべてのオプションをオフのままにして、常に MFA を強制する|

**アクセス制御**

|型|[プロパティ]|値|注|
|:---|:---------|:-----|:----|
|許可|アクセスの許可|True|オン|
||MFA を要求|True|Check|
||デバイスを準拠としてマークする必要がある|False||
||ハイブリッドの Azure AD に参加しているデバイスが必要|False||
||承認済みクライアントアプリを必要とする|False||
||選択したコントロールすべてが必要|True|オン|

> [!NOTE]
> **[**] を選択して、このポリシーを有効にしてください。 また、ポリシーをテストする場合は、[ [対象](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) ] ツールを使用してください。



## <a name="block-clients-that-dont-support-modern-authentication"></a>先進認証をサポートしないクライアントはブロックする
1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。 サインインに成功すると、Azure ダッシュボードが表示されます。

2. 左側のメニューから **[Azure Active Directory]** を選びます。

3. **[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。

4. **[新しいポリシー]** を選びます。

次の表では、このポリシーに対して実装する条件付きアクセスポリシー設定について説明します。

**Assignments**

|型|[プロパティ]|値|注|
|:---|:---------|:-----|:----|
|ユーザーとグループ|含める|ユーザーとグループの選択 – 対象ユーザーを含む特定のセキュリティ グループを選択します|パイロット ユーザーを含むセキュリティ グループから開始します|
||除外|例外セキュリティ グループ、サービス アカウント (アプリ ID)|必要に応じて一時的にメンバーシップを変更します|
|クラウド アプリ|含める|このルールを適用するアプリを選択します。 たとえば、[Exchange Online] を選択します。||
|条件|構成済み|はい|クライアントアプリを構成する|
|クライアント アプリ|構成済み|はい|モバイルアプリとデスクトップクライアント、その他のクライアント (両方を選択する)|

**アクセス制御**

|型|[プロパティ]|値|注|
|:---|:---------|:-----|:----|
|許可|アクセスをブロックする|True|オン|
||MFA を要求|False||
||デバイスを準拠としてマークする必要がある|False||
||ハイブリッドの Azure AD に参加しているデバイスが必要|False||
||承認済みクライアントアプリを必要とする|False||
||選択したコントロールすべてが必要|True|オン|

> [!NOTE]
> **[**] を選択して、このポリシーを有効にしてください。 また、ポリシーをテストする場合は、[ [対象](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) ] ツールを使用してください。



## <a name="high-risk-users-must-change-password"></a>高リスク ユーザーはパスワードを変更する必要がある
すべての危険度の高いユーザーが侵害されたアカウントが、サインイン時にパスワードの変更を強制的に実行するようにするには、次のポリシーを適用する必要があります。

管理者資格情報を使用して [Microsoft Azure ポータル (https://portal.azure.com)](https://portal.azure.com/) にログインしてから、**[Azure AD Identity Protection]、[ユーザーのリスク ポリシー]** の順に移動します。

**Assignments**

|型|[プロパティ]|値|注|
|:---|:---------|:-----|:----|
|Users|含める|[すべてのユーザー]|オン|
||除外|なし||
|条件|ユーザーのリスク|高|オン|

**コントロール**

| 型 | [プロパティ] | 値                  | 注 |
|:-----|:-----------|:------------------------|:------|
|      | アクセス     | SSL 経由でのみ            | True  |
|      | アクセス     | パスワードの変更を必須とする | True  |

**レビュー:** 該当なし

> [!NOTE]
> **[**] を選択して、このポリシーを有効にしてください。 ポリシーをテストする [場合](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) は、[対象] ツールを使用することも検討してください。

## <a name="apply-app-data-protection-policies"></a>アプリデータ保護ポリシーを適用する
アプリ保護ポリシー (APP) は、どのアプリが許可されるか、組織のデータによって実行できるアクションを定義します。 APP で利用可能な選択肢は、組織が特定のニーズに合わせて保護を調整できるようにすることです。 一部のシナリオでは、完全なシナリオを実装するために必要なポリシー設定がわからない場合があります。 組織がモバイルクライアントエンドポイント強化の優先順位を設定するために、Microsoft では、iOS および Android のモバイルアプリ管理用のアプリデータ保護フレームワークに対して分類を導入しています。 

アプリデータ保護フレームワークは3つの異なる構成レベルに編成されており、各レベルは前のレベルから構築されています。 

- **エンタープライズ基本データ保護** (レベル 1) は、アプリが PIN で保護され、暗号化され、選択的なワイプ操作を実行することを保証します。 Android デバイスの場合、このレベルでは Android デバイスの構成証明を検証します。 これは、Exchange Online メールボックスポリシーに類似のデータ保護制御を提供するエントリレベルの構成で、これをアプリに紹介します。 
- **エンタープライズ拡張データ保護** (レベル 2) アプリデータ漏洩防止メカニズムおよび最小 OS 要件について説明します。 これは、職場または学校データにアクセスするほとんどのモバイルユーザーに適用される構成です。 
- **エンタープライズ高データ保護** (レベル 3) は、高度なデータ保護機構、強化された PIN 構成、およびアプリモバイル脅威の防御を導入しています。 この構成は、高リスクデータにアクセスするユーザーに適しています。 

各構成レベルおよび保護する必要のある最小アプリケーションについての特定の推奨事項を確認するには、「 [アプリ保護ポリシーを使用してデータ保護フレームワーク](https://docs.microsoft.com/mem/intune/apps/app-protection-framework)を確認する」を参照してください。 

[Id とデバイスのアクセス構成](microsoft-365-policies-configurations.md)で説明されている原則を使用して、ベースラインおよび機密保護層がレベル2エンタープライズ拡張データ保護設定と緊密にマッピングされます。 高度な規制保護層は、レベル3エンタープライズ高データ保護設定に厳密にマップされます。

|保護レベル |アプリ保護ポリシー  |詳細  |
|---------|---------|---------|
|基準     | [レベル2強化されたデータ保護](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | レベル2で適用されるポリシー設定には、レベル1に推奨されているすべてのポリシー設定が含まれています。さらに、レベル1よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定のみを追加または更新します。         |
|機密     | [レベル2強化されたデータ保護](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | レベル2で適用されるポリシー設定には、レベル1に推奨されているすべてのポリシー設定が含まれています。さらに、レベル1よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定のみを追加または更新します。        |
|厳しい規制     | [レベル3エンタープライズ高データ保護](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)        | レベル3で適用されるポリシー設定には、レベル1および2に推奨されているすべてのポリシー設定が含まれています。さらに、レベル2よりも高度な制御を実装するために、以下のポリシー設定を追加または更新します。        |

データ保護フレームワーク設定を使用して、Microsoft エンドポイントマネージャー内で各プラットフォーム (iOS および Android) に対して新しいアプリ保護ポリシーを作成するには、管理者は次のことを行うことができます。
1. 「 [Microsoft Intune でアプリ保護ポリシーを作成および展開する方法](https://docs.microsoft.com/mem/intune/apps/app-protection-policies)」の手順に従って、ポリシーを手動で作成します。 
2. [Intune の PowerShell スクリプト](https://github.com/microsoftgraph/powershell-intune-samples)を使用して、サンプルの[Intune アプリ保護ポリシー構成フレームワーク JSON テンプレート](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies)をインポートします。

## <a name="require-approved-apps-and-app-protection"></a>承認済みアプリとアプリ保護を必要とする
Intune で適用したアプリ保護ポリシーを適用するには、承認済みのクライアントアプリとアプリ保護ポリシーで設定された条件を要求する条件付きアクセスルールを作成する必要があります。 

アプリ保護ポリシーを適用するには、「 [条件付きアクセスでのクラウドアプリケーションへのアクセスにアプリ保護ポリシーが必要](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)」で説明されている一連のポリシーが必要です。 これらのポリシーは、この推奨される id とアクセス構成ポリシーのセットに含まれています。

承認済みアプリとアプリの保護を必要とする条件付きアクセスルールを作成するには、「 [シナリオ 1: microsoft 365 アプリ](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)には、microsoft 365 の Azure AD 条件付きアクセスポリシーを構成する」を参照してください。これは、IOS および Android 用の Outlook を許可し、OAuth 対応 exchange ActiveSync クライアントによる exchange Online への接続をブロックします

   > [!NOTE]
   > このポリシーにより、モバイルユーザーは適用可能なアプリを使用してすべての Office エンドポイントにアクセスできます。

Exchange Online へのモバイルアクセスを有効にしている場合は、 [ブロック ActiveSync クライアント](secure-email-recommended-policies.md#block-activesync-clients)を実装します。これにより、exchange ActiveSync クライアントは、基本認証を活用して exchange online に接続することができなくなります。 このポリシーは、この記事の上部にある図には示されていません。 [メールを保護するためのポリシーの推奨事項](secure-email-recommended-policies.md)について説明します。

 これらのポリシーは、承認された [クライアントアプリを必要](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) とする grant controls を活用し、 [アプリ保護ポリシーを必要](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)とします。

最後に、iOS および Android デバイス上の他のクライアントアプリに対して従来の認証をブロックすることで、これらのクライアントが条件付きアクセスルールをバイパスできないようにします。 この記事のガイダンスに従っている場合は、 [先進認証をサポートしていないブロッククライアントが](#block-clients-that-dont-support-modern-authentication)既に構成されています。

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several conditional access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>デバイスコンプライアンスポリシーの定義

デバイスコンプライアンスポリシーは、準拠としてマークするためにデバイスが従う必要がある要件を定義します。 Microsoft エンドポイントマネージャー管理センター内から Intune デバイスコンプライアンスポリシーを作成します。

プラットフォームごとにポリシーを作成します。
- Android デバイス管理者
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows Phone 8.1
- Windows 8.1 以降
- Windows 10 以降

デバイスコンプライアンスポリシーを作成するには、管理者の資格情報を使用して[Microsoft Endpoint Manager 管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にログインし、[**デバイス**  >  **コンプライアンスポリシー**のポリシー] に移動し  >  **Policies**ます。 [ **ポリシーの作成**] を選択します。

デバイスコンプライアンスポリシーを展開するには、ユーザーグループに割り当てる必要があります。 ポリシーは、作成して保存した後に割り当てます。 管理センターで、ポリシーを選択し、[ **割り当て**] を選択します。 ポリシーを受信するグループを選択したら、[ **保存** ] を選択してそのグループの割り当てを保存し、ポリシーを展開します。

Intune でコンプライアンスポリシーを作成する詳細な手順については、「Intune ドキュメントの「 [Microsoft intune でコンプライアンスポリシーを作成](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) する」を参照してください。

Windows 10 では、次の設定をお勧めします。

**デバイス正常性: Windows Health 構成証明サービスの評価ルール**

|[プロパティ]|値|注|
|:---------|:-----|:----|
|BitLocker を必須にする|必須||
|デバイスでセキュアブートが有効になっていることが必要|必須||
|コードの整合性を必須にする|必須||


**デバイスのプロパティ**

|型|[プロパティ]|値|注|
|:---|:---------|:-----|:----|
|オペレーティング システムのバージョン|すべて|未構成||

**システム セキュリティ**

|型|[プロパティ]|値|注|
|:---|:---------|:-----|:----|
|Password|モバイルデバイスのロックを解除するためのパスワードを要求する|必須||
||単純なパスワード|ブロック||
||パスワードの種類|既定のデバイス||
||パスワードの最小文字数|6 ||
||パスワードが必要になるまでの最大非アクティブ時間 (分)|15 |この設定は、Android バージョン4.0 以降、または KNOX 4.0 以降でサポートされています。 IOS デバイスでは、iOS 8.0 以降でサポートされています。|
||パスワードの有効期限 (日)|41||
||再利用を防止するための以前のパスワードの数|5 ||
||デバイスがアイドル状態から戻るときにパスワードを要求する (Mobile および Holographic)|必須|Windows 10 以降で使用可能|
|暗号化|デバイス上のデータストレージの暗号化|必須||
|デバイスのセキュリティ|ウォール|必須||
||ウイルス対策|必須||
||ウェア|必須|この設定には、Windows セキュリティセンターに登録されたスパイウェア対策ソリューションが必要です|
|守護|Microsoft Defender マルウェア対策|必須||
||Microsoft Defender マルウェア対策の最小バージョン||Windows 10 デスクトップでのみサポートされています。 Microsoft では、最新バージョン以降のバージョンを5つ以下にすることをお勧めします。|
||Microsoft Defender マルウェア対策の署名が最新の状態になっています|必須||
||リアルタイム保護|必須|Windows 10 デスクトップでのみサポートされています。|

**Microsoft Defender ATP**

|型|[プロパティ]|値|注|
|:---|:---------|:-----|:----|
|Microsoft Defender Advanced Threat Protection ルール|デバイスがコンピューターのリスクスコアの下または下にある必要があります。|中||


## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>準拠 Pc を必要とする (ただし、準拠する電話やタブレットではない)
準拠している Pc を必要とするポリシーを追加する前に、管理するデバイスを Intune に登録してください。 デバイスが目的のユーザーを所有していることを保証するために、デバイスを Intune に登録する前に、多要素認証を使用することをお勧めします。 

準拠している Pc を要求するには:

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。 サインインに成功すると、Azure ダッシュボードが表示されます。

2. 左側のメニューから **[Azure Active Directory]** を選びます。

3. **[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。

4. **[新しいポリシー]** を選びます。

5. ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。

6. **[クラウド アプリ]** を選びます。

7. **[アプリの選択**] を選択し、[**クラウドアプリ**] リストから目的のアプリを選択します。 たとえば、[Exchange Online] を選択します。 **[選択**して**完了**] を選択します。

8. 準拠している Pc を必要とするが、準拠している電話やタブレットではないものを要求するには、 **条件** と **デバイスプラットフォーム**を選択します **[Select device プラットフォーム]** を選択して、[ **Windows**と**macOS**] を選択します。

9. **[アクセス制御]** セクションから **[許可]** を選びます。

10. [ **アクセス許可**] を選択し、[ **デバイスが準拠していることをマークする必要がある**] を選択します。 複数のコントロールの場合は、[選択し **たすべてのコントロールを必要とする**] を選択し、[ **選択**] を選択します。 

11. **[作成]** を選択します。

準拠している Pc *と* モバイルデバイスを必要とする目的では、プラットフォームを選択しないでください。 これにより、すべてのデバイスのコンプライアンスを強制します。 

## <a name="require-compliant-pcs-and-mobile-devices"></a>準拠 *して* いる pc とモバイルデバイスが必要

すべてのデバイスのコンプライアンスを要求するには、次のようにします。

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。 サインインに成功すると、Azure ダッシュボードが表示されます。

2. 左側のメニューから **[Azure Active Directory]** を選びます。

3. **[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。

4. **[新しいポリシー]** を選びます。

5. ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。

6. **[クラウド アプリ]** を選びます。

7. **[アプリの選択**] を選択し、[**クラウドアプリ**] リストから目的のアプリを選択します。 たとえば、[Exchange Online] を選択します。 **[選択**して**完了**] を選択します。

8. **[アクセス制御]** セクションから **[許可]** を選びます。

9. [ **アクセス許可**] を選択し、[ **デバイスが準拠していることをマークする必要がある**] を選択します。 複数のコントロールの場合は、[選択し **たすべてのコントロールを必要とする**] を選択し、[ **選択**] を選択します。 

10. **[作成]** を選択します。

このポリシーを作成するときは、プラットフォームを選択しないでください。 これにより、準拠しているデバイスが強制できます。


## <a name="next-steps"></a>次の手順

[電子メールをセキュリティで保護するためのポリシーの推奨事項について学びます](secure-email-recommended-policies.md)
