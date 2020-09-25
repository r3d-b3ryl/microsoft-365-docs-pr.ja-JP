---
title: 一般的な id およびデバイスアクセスポリシー-Microsoft 365 for enterprise |Microsoft Docs
description: 推奨される一般的な id およびデバイスアクセスポリシーと構成について説明します。
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
ms.openlocfilehash: 6a8ab25a1bce4355e63482b8450412884a9f0faf
ms.sourcegitcommit: 96b4593becc9450af136c528844e858c6e88b5a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269407"
---
# <a name="common-identity-and-device-access-policies"></a>共通 ID とデバイスのアクセス ポリシー

この記事では、Azure Active Directory (Azure AD) アプリケーションプロキシで公開されているオンプレミスアプリケーションを含む、Microsoft 365 クラウドサービスへのアクセスを保護するための一般的な推奨ポリシーについて説明します。 

このガイダンスでは、新しくプロビジョニングされた環境に推奨されるポリシーを展開する方法について説明します。 個別のラボ環境でこれらのポリシーを設定することにより、展開をステージングおよび運用環境にステージングする前に、推奨ポリシーを理解し、評価することができます。 新しくプロビジョニングされた環境は、評価のニーズを反映するために、クラウド専用またはハイブリッドにすることができます。  

## <a name="policy-set"></a>ポリシーセット 

次の図は、推奨されるポリシーセットを示しています。 この図は、各ポリシーが適用される保護層と、それらのポリシーが Pc、電話、タブレット、または両方のカテゴリのデバイスに適用されるかどうかを示しています。 また、これらのポリシーを構成する場所も示されます。

[ ![ Id とデバイスのアクセスを構成するための一般的なポリシー](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [この画像の大規模なバージョンの表示](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

以下に、個々のポリシーへのリンクを含む1ページの PDF の概要を示します。

[![Microsoft 365 配布資料の Id とデバイス保護のサムネイル画像](../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br/>  PDF とし[て表示する](../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \|[PDF としてダウンロードする](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)  

この記事の残りの部分では、これらのポリシーを構成する方法について説明します。 

>[!Note]
>デバイスが目的のユーザーを所有していることを確認するために、Intune にデバイスを登録する前に、複数要素認証 (MFA) の使用を要求することをお勧めします。 デバイスコンプライアンスポリシーを適用する前に、Intune にデバイスを登録する必要があります。
>

これらのタスクを実行するための時間を提供するために、この表に記載されている順序で基準ポリシーを実装することをお勧めします。 ただし、機密性が高く規制された保護レベルの MFA ポリシーは、いつでも実装できます。

|保護レベル|ポリシー|詳細情報|
|:---------------|:-------|:----------------|
|**Baseline**|[サインインリスクが*中*または*高*の場合は MFA を必須にする](#require-mfa-based-on-sign-in-risk)| |
|        |[先進認証をサポートしないクライアントはブロックする](#block-clients-that-dont-support-modern-authentication)|モダン認証を使用していないクライアントは、条件付きアクセスポリシーをバイパスすることがあるため、これらをブロックすることが重要です。|
|        |[高リスク ユーザーはパスワードを変更する必要がある](#high-risk-users-must-change-password)|アカウントの高リスクアクティビティが検出された場合に、サインイン時にユーザーにパスワードを変更することを強制します。|
|        |[アプリデータ保護ポリシーを適用する](#apply-app-data-protection-policies)|プラットフォームごとに1つの Intune アプリ保護ポリシー (Windows、iOS/iPadOS、Android)。|
|        |[承認済みアプリとアプリ保護を必要とする](#require-approved-apps-and-app-protection)|IOS、iPadOS、または Android を使用して、携帯電話やタブレットにモバイルアプリの保護を適用します。|
|        |[デバイスコンプライアンスポリシーの定義](#define-device-compliance-policies)|プラットフォームごとに1つのポリシー。|
|        |[準拠 PC が必要](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Windows または MacOS を使用して、Pc の Intune 管理を強制します。|
|**機密**|[サインインリスクが*低*、*中*、*高*のときに MFA を必要とする](#require-mfa-based-on-sign-in-risk)| |
|         |[準拠 *して* いる pc とモバイルデバイスが必要](#require-compliant-pcs-and-mobile-devices)|Pc (Windows または Os) と、電話またはタブレット (iOS、iPadOS、Android) の両方に Intune 管理を強制します。|
|**厳しく規制**|[*常に* MFA が必要](#require-mfa-based-on-sign-in-risk)|
| | | |

## <a name="assigning-policies-to-groups-and-users"></a>グループとユーザーへのポリシーの割り当て

ポリシーを構成する前に、各層の保護に使用している Azure AD グループを特定します。 通常、ベースライン保護は組織内の全員に適用されます。 ベースラインと機密保護の両方に含まれているユーザーには、適用されているすべてのベースラインポリシーと、機密ポリシーが適用されます。 保護は累積され、最も制限の厳しいポリシーが適用されます。 

条件付きアクセスの除外に対して Azure AD グループを作成することをお勧めします。 このグループを、[**割り当て**] セクションの [**ユーザーとグループ**] の設定の [**除外**] の値にあるすべての条件付きアクセスポリシーに追加します。 これにより、アクセスの問題のトラブルシューティングを行っている間、ユーザーにアクセス権を与えることができます。 これは、一時的なソリューションとしてのみお勧めします。 このグループを監視して変更を確認し、除外グループが意図したとおりにのみ使用されていることを確認します。 

ここでは、MFA を必要とするグループ割り当てと除外の例を示します。

![MFA ポリシーのグループ割り当てと除外の例](../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

結果は次のとおりです。

- サインインリスクが中または高である場合は、すべてのユーザーが MFA を使用する必要があります。

- 役員スタッフグループのメンバーは、サインインリスクが低、中、高のときに MFA を使用する必要があります。

  この場合、重役スタッフグループのメンバーは、ベースラインと機密の条件付きアクセスポリシーの両方に一致します。 両方のポリシーのアクセス制御は組み合わされています。この場合は、機密の条件付きアクセスポリシーに相当します。

- Top Secret プロジェクト X グループのメンバーは、常に MFA を使用する必要があります。

  この場合、Top Secret プロジェクト X グループのメンバーは、ベースラインと厳しく規制された条件付きアクセスポリシーの両方と一致します。 両方のポリシーのアクセス制御が組み合わされています。 高度に規制された条件付きアクセスポリシーのアクセス制御の方が制限が多いため、これが使用されます。

グループとユーザーに高レベルの保護を適用する場合は注意が必要です。 たとえば、Top Secret プロジェクト X グループのメンバーは、プロジェクト X の厳しい規制コンテンツで作業していない場合でも、サインインするたびに MFA を使用する必要があります。  

これらの推奨事項の一部として作成されたすべての Azure AD グループは、Microsoft 365 グループとして作成する必要があります。 これは、Microsoft Teams および SharePoint でドキュメントを保護するときに機密ラベルを展開する際に重要です。

![Microsoft 365 グループを作成するための画面キャプチャ](../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>サインインリスクに基づいて MFA を必須にする

ユーザーに対して、を使用する前に MFA を登録する必要があります。 Microsoft 365 E5、Microsoft 365 E3 with Identity & Threat Protection アドオン、Office 365、EMS E5、または個別の Azure AD Premium のライセンスを持っている場合は、Azure AD Id 保護で MFA 登録ポリシーを使用して、ユーザーに MFA を登録するよう要求することができます。 [前提条件](identity-access-prerequisites.md)となるのは、すべてのユーザーを MFA で登録することです。

ユーザーを登録した後、新しい条件付きアクセスポリシーを使用して、サインインに MFA を要求することができます。

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。
2. Azure サービスの一覧で、[ **Azure Active Directory**] を選択します。
3. [ **管理** ] リストで、[ **セキュリティ**] を選択してから、[ **条件付きアクセス**] を選択します。
4. [ **新しいポリシー** ] を選択し、新しいポリシーの名前を入力します。

次の表では、サインインリスクに基づいて MFA を必要とする条件付きアクセスポリシー設定について説明します。

[ **割り当て** ] セクションで、次の手順を実行します。

|設定|[プロパティ]|値|注|
|:---|:---------|:-----|:----|
|ユーザーとグループ|含める| [ユーザーとグループ > ユーザーとグループ **] を選択**します。対象ユーザーアカウントを含む特定のグループを選択します。 |パイロットユーザーアカウントを含むグループから始めます。|
||除外| [**ユーザーとグループ**]: 条件付きアクセスの例外グループを選択します。サービスアカウント (アプリ id)。|メンバーシップは、必要に応じて一時的に変更する必要があります。|
|クラウドアプリまたはアクション| **クラウドアプリ > 含める** | **[アプリの選択**]: このポリシーを適用するアプリを選択します。 たとえば、[Exchange Online] を選択します。||
|条件| | |環境とニーズに固有の条件を構成します。|
||サインイン リスク||次の表のガイダンスを参照してください。|
|||||

**サインインリスクの条件の設定**

対象とする保護レベルに基づいて、リスクレベルの設定を適用します。

|保護レベル|必要なリスクレベルの値|Action|
|:---------|:-----|:----|
|基準|高、中|両方をチェックします。|
|機密|高、中、低|3つすべてをチェックします。|
|厳しく規制| |常に MFA を強制するには、すべてのオプションをオフのままにします。|
||||

[ **アクセス制御** ] セクションで、次の操作を行います。

|設定|[プロパティ]|値|Action|
|:---|:---------|:-----|:----|
|許可|**Grant access**| | Select |
|||**多要素認証を必要とする**| 小切手 |
||**選択したコントロールすべてが必要** ||Select|
|||||

**[選択]** を選択して、**許可**の設定を保存します。

最後に、 **[** **有効なポリシー**] に対して [オン] を選択し、[ **作成**] を選択します。

また、ポリシーをテストする場合は、[ [対象](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) ] ツールを使用してください。

## <a name="block-clients-that-dont-support-modern-authentication"></a>先進認証をサポートしないクライアントはブロックする

モダン認証をサポートしていないクライアントをブロックする条件付きアクセスポリシーについては、これらの表の設定を使用します。

Suppport モダン認証を実行する Microsoft 365 のクライアントの一覧については、 [この記事](microsoft-365-client-support-modern-authentication.md) を参照してください。

[ **割り当て** ] セクションで、次の手順を実行します。

|設定|[プロパティ]|値|注|
|:---|:---------|:-----|:----|
|ユーザーとグループ|含める| [ユーザーとグループ > ユーザーとグループ **] を選択**します。対象ユーザーアカウントを含む特定のグループを選択します。 |パイロットユーザーアカウントを含むグループから始めます。|
||除外| [**ユーザーとグループ**]: 条件付きアクセスの例外グループを選択します。サービスアカウント (アプリ id)。|メンバーシップは、必要に応じて一時的に変更する必要があります。|
|クラウドアプリまたはアクション|**クラウドアプリ > 含める**| **[アプリの選択**]: モダン認証をサポートしていないクライアントに対応するアプリを選択します。||
|条件| **クライアント アプリ** | **構成**には [**はい]** を選択します。 <br> **ブラウザー**と**モバイルアプリおよびデスクトップクライアント**のチェックマークをクリアする | |
||||

[ **アクセス制御** ] セクションで、次の操作を行います。

|設定|[プロパティ]|値|Action|
|:---|:---------|:-----|:----|
|許可|**アクセスをブロックする**| | Select |
||**選択したコントロールすべてが必要** ||Select|
|||||

**[選択]** を選択して、**許可**の設定を保存します。

最後に、 **[** **有効なポリシー**] に対して [オン] を選択し、[ **作成**] を選択します。

ポリシーをテストするには、[ [対象](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) ] ツールを使用することを検討してください。

Exchange Online の場合は、認証ポリシーを使用して [基本認証を無効](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)にすることができます。これにより、すべてのクライアントアクセス要求で先進認証を使用することが強制されます。

## <a name="high-risk-users-must-change-password"></a>高リスク ユーザーはパスワードを変更する必要がある

すべての危険度の高いユーザーが侵害されたアカウントが、サインイン時にパスワードの変更を強制的に実行するようにするには、次のポリシーを適用する必要があります。

管理者資格情報を使用して [Microsoft Azure ポータル (https://portal.azure.com)](https://portal.azure.com/) にログインしてから、**[Azure AD Identity Protection]、[ユーザーのリスク ポリシー]** の順に移動します。

[ **割り当て** ] セクションで、次の手順を実行します。

|型|[プロパティ]|値|Action|
|:---|:---------|:-----|:----|
|Users|含める|**[すべてのユーザー]**|Select|
|ユーザーのリスク| **High**||Select|
|||||

2番目の **割り当て** セクションで、次の手順を実行します。

| 型 | [プロパティ] | 値                  | Action |
|:-----|:-----------|:------------------------|:------|
| Access | **SSL 経由でのみ** |  | Select  |
|      |     | **パスワードの変更を必須とする** | 小切手  |
|||||

[ **完了** ] を選択して、 **アクセス** 設定を保存します。

最後に [ポリシーを**強制****する]** を選択し、[**保存**] を選択します。

ポリシーをテストするには、[ [対象](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) ] ツールを使用することを検討してください。

このポリシーは、「 [AZURE AD パスワード保護を構成](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)する」と組み合わせて使用します。これにより、既知の弱いパスワードとその亜種と、組織固有のその他の弱い用語を検出してブロックします。 Azure AD パスワード保護を使用すると、変更されたパスワードが強固なパスワードになることが保証されます。

## <a name="apply-app-data-protection-policies"></a>アプリデータ保護ポリシーを適用する

アプリ保護ポリシー (APP) は、どのアプリが許可されるか、組織のデータによって実行できるアクションを定義します。 APP で利用可能な選択肢は、組織が特定のニーズに合わせて保護を調整できるようにすることです。 一部のシナリオでは、完全なシナリオを実装するために必要なポリシー設定がわからない場合があります。 組織がモバイルクライアントエンドポイント強化の優先順位を設定するために、Microsoft では、iOS および Android のモバイルアプリ管理用のアプリデータ保護フレームワークに対して分類を導入しています。 

アプリデータ保護フレームワークは3つの異なる構成レベルに編成されており、各レベルは前のレベルから構築されています。 

- **エンタープライズ基本データ保護** (レベル 1) は、アプリが PIN で保護され、暗号化され、選択的なワイプ操作を実行することを保証します。 Android デバイスの場合、このレベルでは Android デバイスの構成証明を検証します。 これは、Exchange Online メールボックスポリシーに類似のデータ保護制御を提供するエントリレベルの構成で、これをアプリに紹介します。 
- **エンタープライズ拡張データ保護** (レベル 2) アプリデータ漏洩防止メカニズムおよび最小 OS 要件について説明します。 これは、職場または学校データにアクセスするほとんどのモバイルユーザーに適用される構成です。 
- **エンタープライズ高データ保護** (レベル 3) は、高度なデータ保護機構、強化された PIN 構成、およびアプリモバイル脅威の防御を導入しています。 この構成は、高リスクデータにアクセスするユーザーに適しています。 

各構成レベルおよび保護する必要のある最小アプリケーションについての特定の推奨事項を確認するには、「 [アプリ保護ポリシーを使用してデータ保護フレームワーク](https://docs.microsoft.com/mem/intune/apps/app-protection-framework)を確認する」を参照してください。 

[Id とデバイスのアクセス構成](microsoft-365-policies-configurations.md)で説明されている原則を使用して、ベースラインおよび機密保護層がレベル2エンタープライズ拡張データ保護設定と緊密にマッピングされます。 高度な規制保護層は、レベル3エンタープライズ高データ保護設定に厳密にマップされます。

|保護レベル |アプリ保護ポリシー  |詳細情報  |
|---------|---------|---------|
|基準     | [レベル2強化されたデータ保護](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | レベル2で適用されるポリシー設定には、レベル1に推奨されているすべてのポリシー設定が含まれています。さらに、レベル1よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定のみを追加または更新します。         |
|機密     | [レベル2強化されたデータ保護](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | レベル2で適用されるポリシー設定には、レベル1に推奨されているすべてのポリシー設定が含まれています。さらに、レベル1よりも多くのコントロールとより高度な構成を実装するために、以下のポリシー設定のみを追加または更新します。        |
|厳しい規制     | [レベル3エンタープライズ高データ保護](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)        | レベル3で適用されるポリシー設定には、レベル1および2に推奨されているすべてのポリシー設定が含まれています。さらに、レベル2よりも高度な制御を実装するために、以下のポリシー設定を追加または更新します。        |

データ保護フレームワーク設定を使用して、Microsoft エンドポイントマネージャー内の各プラットフォーム (iOS および Android) に対して新しいアプリ保護ポリシーを作成するには、次のことを行うことができます。

1. 「 [Microsoft Intune でアプリ保護ポリシーを作成および展開する方法](https://docs.microsoft.com/mem/intune/apps/app-protection-policies)」の手順に従って、ポリシーを手動で作成します。 
2. [Intune の PowerShell スクリプト](https://github.com/microsoftgraph/powershell-intune-samples)を使用して、サンプルの[Intune アプリ保護ポリシー構成フレームワーク JSON テンプレート](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies)をインポートします。

## <a name="require-approved-apps-and-app-protection"></a>承認済みアプリとアプリ保護を必要とする

Intune で適用したアプリ保護ポリシーを強制するには、承認されたクライアントアプリとアプリ保護ポリシーで設定された条件を要求するための条件付きアクセスポリシーを作成する必要があります。 

アプリ保護ポリシーを適用するには、「 [条件付きアクセスでのクラウドアプリケーションへのアクセスにアプリ保護ポリシーが必要](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)」で説明されている一連のポリシーが必要です。 これらのポリシーは、この推奨される id とアクセス構成ポリシーのセットに含まれています。

承認済みアプリとアプリの保護を必要とする条件付きアクセスポリシーを作成するには、「 [シナリオ 1: microsoft 365 アプリ](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)には、microsoft 365 の Azure AD 条件付きアクセスポリシーを構成する」を参照してください。これは、IOS および Android 用の Outlook を許可し、OAuth 対応 exchange ActiveSync クライアントが exchange Online に接続できないようにするためです

   > [!NOTE]
   > このポリシーにより、モバイルユーザーは適用可能なアプリを使用してすべての Office エンドポイントにアクセスできます。

Exchange Online へのモバイルアクセスを有効にしている場合は、 [ブロック ActiveSync クライアント](secure-email-recommended-policies.md#block-activesync-clients)を実装します。これにより、exchange ActiveSync クライアントは、基本認証を活用して exchange online に接続することができなくなります。 このポリシーは、この記事の上部にある図には示されていません。 [メールを保護するためのポリシーの推奨事項](secure-email-recommended-policies.md)について説明します。

 これらのポリシーは、承認された [クライアントアプリを必要](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) とする grant controls を活用し、 [アプリ保護ポリシーを必要](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)とします。

最後に、iOS および Android デバイス上の他のクライアントアプリに対して従来の認証をブロックすることで、これらのクライアントが条件付きアクセスポリシーをバイパスできないようにします。 この記事のガイダンスに従っている場合は、 [先進認証をサポートしていないブロッククライアントが](#block-clients-that-dont-support-modern-authentication)既に構成されています。

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>デバイスコンプライアンスポリシーの定義

デバイスコンプライアンスポリシーは、デバイスが準拠として判断するために満たす必要がある要件を定義します。 Intune デバイスコンプライアンスポリシーは、Microsoft エンドポイントマネージャー管理センター内から作成します。

各 PC、電話、またはタブレットプラットフォームに対してポリシーを作成する必要があります。

- Android デバイス管理者
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 以降
- Windows 10 以降

デバイスコンプライアンスポリシーを作成するには、管理者の資格情報を使用して[Microsoft Endpoint Manager 管理センター](https://endpoint.microsoft.com)にログインし、[**デバイス**  >  **コンプライアンスポリシー**のポリシー] に移動し  >  **Policies**ます。 [ **ポリシーの作成**] を選択します。

デバイスコンプライアンスポリシーを展開するには、ユーザーグループに割り当てる必要があります。 ポリシーは、作成して保存した後に割り当てます。 管理センターで、ポリシーを選択し、[ **割り当て**] を選択します。 ポリシーを受信するグループを選択したら、[ **保存** ] を選択してそのグループの割り当てを保存し、ポリシーを展開します。

Intune でコンプライアンスポリシーを作成する詳細な手順については、「Intune ドキュメントの「 [Microsoft intune でコンプライアンスポリシーを作成](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) する」を参照してください。

### <a name="recommended-settings-for-windows-10-and-later"></a>Windows 10 以降の推奨設定

次の設定は、「 **手順 2: コンプライアンス設定**」でポリシー作成プロセスを構成して、Windows 10 以降を実行している pc に推奨されます。

**デバイスの > 正常性構成証明サービスの評価ルール**については、次の表を参照してください。

|プロパティ|値|Action|
|:---------|:-----|:----|
|BitLocker を必須にする|必須| Select |
|デバイスでセキュアブートが有効になっていることが必要|必須| Select |
|コードの整合性を必須にする|必須| Select |
||||

**デバイスのプロパティ**については、IT およびセキュリティポリシーに基づいてオペレーティングシステムのバージョンに適切な値を指定します。

**構成マネージャーのコンプライアンス**の場合は、[**必須**] を選択します。

**システムセキュリティ**については、次の表を参照してください。

|型|[プロパティ]|値|Action|
|:---|:---------|:-----|:----|
|Password|モバイルデバイスのロックを解除するためのパスワードを要求する|必須| Select |
||単純なパスワード|ブロック|Select|
||パスワードの種類|既定のデバイス|Select|
||パスワードの最小文字数|6 |型|
||パスワードが必要になるまでの最大非アクティブ時間 (分)|15 |型 <br>この設定は、Android バージョン4.0 以降、または KNOX 4.0 以降でサポートされています。 IOS デバイスでは、iOS 8.0 以降でサポートされています。|
||パスワードの有効期限 (日)|41|型|
||再利用を防止するための以前のパスワードの数|5 |型|
||デバイスがアイドル状態から戻るときにパスワードを要求する (Mobile および Holographic)|必須|Windows 10 以降で使用可能|
|暗号化|デバイス上のデータストレージの暗号化|必須|Select|
|デバイスのセキュリティ|ウォール|必須|Select|
||ウイルス対策|必須|Select|
||ウェア|必須|Select <br> この設定には、Windows セキュリティセンターに登録されたスパイウェア対策ソリューションが必要です。|
|守護|Microsoft Defender マルウェア対策|必須|Select|
||Microsoft Defender マルウェア対策の最小バージョン||型 <br> Windows 10 デスクトップでのみサポートされています。 Microsoft では、最新バージョン以降のバージョンを5つ以下にすることをお勧めします。|
||Microsoft Defender マルウェア対策の署名が最新の状態になっています|必須|Select|
||リアルタイム保護|必須|Select <br>Windows 10 デスクトップでのみサポートされています。|
|||||

**Microsoft Defender ATP**

|型|[プロパティ]|値|Action|
|:---|:---------|:-----|:----|
|Microsoft Defender Advanced Threat Protection ルール|デバイスがコンピューターのリスクスコアの下または下にある必要があります。|中|Select|
|||||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>準拠 Pc を必要とする (ただし、準拠する電話やタブレットではない)

準拠している Pc を必要とするポリシーを追加する前に、管理するデバイスを Intune に登録してください。 デバイスが目的のユーザーを所有していることを保証するために、デバイスを Intune に登録する前に、多要素認証を使用することをお勧めします。 

準拠している Pc を要求するには:

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。
2. Azure サービスの一覧で、[ **Azure Active Directory**] を選択します。
3. [ **管理** ] リストで、[ **セキュリティ**] を選択してから、[ **条件付きアクセス**] を選択します。
4. [ **新しいポリシー** ] を選択し、新しいポリシーの名前を入力します。

5. [ **割り当て**] で、[ **ユーザーとグループ** ] を選択し、ポリシーを適用するユーザーを指定します。 また、条件付きアクセス除外グループを除外します。

6. [ **割り当て**] で、[ **クラウドアプリ] または [アクション**] を選択します。

7. **Include**で、[**アプリの選択 >** 選択] を選択し、**クラウドアプリ**の一覧から目的のアプリを選択します。 たとえば、[Exchange Online] を選択します。 [完了時に **選択]** を選択します。

8. 準拠している Pc (かつ、準拠していない電話やタブレットではない) を要求するには、[ **割り当て**] の下で [ **条件 > デバイスプラットフォーム**] を選択します。 [**構成**] で [**はい]** を選択します。 [  **デバイスプラットフォームの選択**] を選択し、[ **Windows** と **macOS**] を選択して、[ **完了**] を選択します。

9. [ **アクセス制御**] で、[ **付与** ] を選択します。

10. [ **アクセス許可** ] を選択し、[ **デバイスが準拠していることをマーク**する] をオンにします。 複数のコントロールの場合は、[ **選択したすべてのコントロールを必要とする**] を選択します。 完了したら、 **[選択]** を選択します。 

10. [有効な**ポリシー**] で **[オン]** を選択し、[**作成**] を選択します。

>[!Note]
>このポリシーを有効にする前に、デバイスが準拠していることを確認してください。 そうしないと、ロックアウトされ、ユーザーアカウントが条件付きアクセス除外グループに追加されるまで、このポリシーを変更できなくなります。
>

## <a name="require-compliant-pcs-and-mobile-devices"></a>準拠 *して* いる pc とモバイルデバイスが必要

すべてのデバイスのコンプライアンスを要求するには、次のようにします。

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。
2. Azure サービスの一覧で、[ **Azure Active Directory**] を選択します。
3. [ **管理** ] リストで、[ **セキュリティ**] を選択してから、[ **条件付きアクセス**] を選択します。
4. [ **新しいポリシー** ] を選択し、新しいポリシーの名前を入力します。

5. [ **割り当て**] で、[ **ユーザーとグループ** ] を選択し、ポリシーを適用するユーザーを指定します。 また、条件付きアクセス除外グループを除外します。

6. [ **割り当て**] で、[ **クラウドアプリ] または [アクション**] を選択します。

7. **Include**で、[**アプリの選択 >** 選択] を選択し、**クラウドアプリ**の一覧から目的のアプリを選択します。 たとえば、[Exchange Online] を選択します。 [完了時に **選択]** を選択します。

8. [ **アクセス制御**] で、[ **付与** ] を選択します。

9. [ **アクセス許可** ] を選択し、[ **デバイスが準拠していることをマーク**する] をオンにします。 複数のコントロールの場合は、[ **選択したすべてのコントロールを必要とする**] を選択します。 完了したら、 **[選択]** を選択します。 

10. [有効な**ポリシー**] で **[オン]** を選択し、[**作成**] を選択します。

>[!Note]
>このポリシーを有効にする前に、デバイスが準拠していることを確認してください。 そうしないと、ロックアウトされ、ユーザーアカウントが条件付きアクセス除外グループに追加されるまで、このポリシーを変更できなくなります。
>

## <a name="next-step"></a>次の手順

[![手順 3: ゲストユーザーと外部ユーザーのポリシー](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[ゲストユーザーと外部ユーザーのポリシー推奨事項について説明します。](identity-access-policies-guest-access.md)
