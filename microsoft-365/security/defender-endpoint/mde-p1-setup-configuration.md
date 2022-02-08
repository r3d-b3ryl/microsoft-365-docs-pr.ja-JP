---
title: Microsoft Defender for Endpoint Plan 1 のセットアップと構成
description: Defender for Endpoint Plan 1 を設定および構成する方法について説明します。 要件を確認し、ロールアウトを計画し、環境をセットアップします。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 01/14/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection:
  - M365-security-compliance
  - m365initiative-defender-endpoint
---

# <a name="set-up-and-configure-microsoft-defender-for-endpoint-plan-1"></a>Microsoft Defender for Endpoint Plan 1 のセットアップと構成

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

この記事では、Defender for Endpoint Plan 1 をセットアップして構成する方法について説明します。 サポートを受け取っている場合でも、自分で行っている場合でも、この記事を展開全体のガイドとして使用できます。  

## <a name="the-setup-and-configuration-process"></a>セットアップと構成プロセス

:::image type="content" source="images/mde-p1-deploymentflow.png" alt-text="Microsoft Defender for Endpoint Plan 1 のセットアップと展開フロー":::

Defender for Endpoint Plan 1 の一般的なセットアップと構成プロセスは次のとおりです。 <br/><br/>


| 番号  | 手順  | 説明  |
|:---------:|:---------|:---------|
| 1 | [要件を確認する](#review-the-requirements)  | ライセンス、ブラウザー、オペレーティング システム、およびデータセンターの要件の一覧   |
| 2 | [展開の計画](#plan-your-deployment) | 考慮すべきいくつかの展開方法の一覧と、使用する方法を決定する際に役立つその他のリソースへのリンクが含まれています。  |
| 3 | [テナント環境のセットアップ](#set-up-your-tenant-environment) | テナント環境をセットアップするタスクの一覧 |
| 4 | [役割とアクセス許可の割り当て](#assign-roles-and-permissions) | セキュリティ チームで考慮する役割とアクセス許可の一覧 <br/><br/>**ヒント**: 役割とアクセス許可が割り当てられるとすぐに、セキュリティ チームは新しいポータルを使用Microsoft 365 Defenderできます。 詳細については、「 [Getting started」を参照してください](mde-plan1-getting-started.md)。 |
| 5 | [Defender for Endpoint へのオンボード](#onboard-to-defender-for-endpoint) | Defender for Endpoint Plan 1 にオンボードするオペレーティング システム別のいくつかのメソッドの一覧と、各メソッドの詳細情報へのリンクが含まれています  |
| 6  | [次世代の保護を構成する](#configure-next-generation-protection) | デバイスで次世代の保護設定を構成する方法についてMicrosoft エンドポイント マネージャー  |
| 7  | [攻撃表面の縮小機能を構成する](#configure-your-attack-surface-reduction-capabilities)        | 構成できる攻撃表面の縮小機能の種類と、より多くのリソースへのリンクを含む手順を示します。  |
 
## <a name="review-the-requirements"></a>システム要件を確認する

次の表に、Defender for Endpoint Plan 1 の基本的な要件を示します。<br/><br/>

| 要件 | 説明 |
|:---|:---|
| ライセンスの要件 | Defender for Endpoint Plan 1 (以前は Microsoft Defender for Endpoint Lite と呼ばば)|
| ブラウザー要件 | Microsoft Edge <br/> Internet Explorerバージョン 11 <br/> Google Chrome |
| オペレーティング システム | Windows 10バージョン 1709 以降 <br/>macOS: 11.5 (Big Sur), 10.15.7 (Catalina), or 10.14.6 (Mojave) <br/>iOS <br/>Android OS  |
| Datacenter | 次のいずれかのデータセンターの場所。 <br/>- 欧州連合 <br/>- イギリス <br/>- 米国 |


## <a name="plan-your-deployment"></a>展開の計画

展開を計画する場合は、いくつかの異なるアーキテクチャと展開方法から選択できます。 各組織は一意なので、次の表に示すいくつかのオプションを検討する必要があります。 <br/><br/>

| メソッド | 説明 |
|:---|:---|
| [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Microsoft エンドポイント マネージャー) | Intune を使用してクラウド ネイティブ環境のエンドポイントを管理する |
| [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)[および構成マネージャー](/mem/configmgr/core/understand/introduction) (Microsoft エンドポイント マネージャー) | Intune と Configuration Manager を使用して、オンプレミス環境とクラウド環境にまたがるエンドポイントとワークロードを管理する |
| [Configuration Manager](/mem/configmgr/core/understand/introduction) | Configuration Manager を使用して、Defender for Endpoint のクラウドベースの機能を使用してオンプレミスのエンドポイントを保護する |
| ポータルからダウンロードしたローカル Microsoft 365 Defender スクリプト | エンドポイントでローカル スクリプトを使用してパイロットを実行するか、少数のデバイスをオンボードする |

展開オプションの詳細については、「Defender [for Endpoint の展開を計画する」を参照してください](deployment-strategy.md)。 次のポスターをダウンロードします。 

[:::image type="content" source="../../media/defender-endpoint/mde-deployment-strategy.png" alt-text="展開戦略ポスターのサムネイル":::](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)

**[展開ポスターを取得する](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)**

> [!TIP]
> 展開の計画の詳細については、「 [Plan your Microsoft Defender for Endpoint deployment」を参照してください](deployment-strategy.md)。

## <a name="set-up-your-tenant-environment"></a>テナント環境のセットアップ

テナント環境のセットアップには、次のようなタスクが含まれます。

- ライセンスの確認
- テナントの構成
- プロキシ設定の構成 (必要な場合のみ)
- センサーが正しく動作し、Defender for Endpoint にデータを報告する 

これらのタスクは、Defender for Endpoint のセットアップ フェーズに含まれています。 「 [エンドポイントの Defender をセットアップする」を参照してください](production-deployment.md)。

## <a name="assign-roles-and-permissions"></a>役割とアクセス許可の割り当て

Microsoft 365 Defender ポータルにアクセスしたり、Defender for Endpoint の設定を構成したり、検出された脅威に対して応答アクションを実行するなどのタスクを実行するには、適切なアクセス許可を割り当てる必要があります。 Defender for Endpoint では、アプリケーション[内で組み込みのAzure Active Directory](/azure/active-directory/roles/permissions-reference)。 

Microsoft では、タスクを実行するために必要なレベルのアクセス許可のみをユーザーに割り当てる必要があります。 基本的なアクセス許可管理を使用するか、役割ベースのアクセス制御 (RBAC) を使用してアクセス許可 [を割り](rbac.md) 当てることができます。 

- 基本的なアクセス許可管理では、グローバル管理者とセキュリティ管理者はフル アクセス権を持ち、セキュリティ リーダーは読み取り専用アクセス権を持っています。
- RBAC を使用すると、より詳細なアクセス許可を、より多くの役割を通じて設定できます。 たとえば、セキュリティ リーダー、セキュリティオペレーター、セキュリティ管理者、エンドポイント管理者などです。


次の表では、組織内の Defender for Endpoint で考慮する重要な役割について説明します。 <br/><br/>

| 役割 | 説明 |
|:---|:---|
| グローバル管理者 (グローバル管理者とも呼ばれます) <br/><br/> *ベスト プラクティスとして、グローバル管理者の数を制限します。* | グローバル管理者は、あらゆる種類のタスクを実行できます。 既定では、Microsoft Defender for Endpoint Plan 1 Microsoft 365または Microsoft Defender の会社にサインアップしたユーザーは、グローバル管理者です。 <br/><br/> グローバル管理者は、次のようなすべてのポータルMicrosoft 365設定にアクセス/変更できます。 <br/>- Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) <br/>- Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) <br/>- Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com))  |
| セキュリティ管理者 (セキュリティ管理者とも呼ばれます) | セキュリティ管理者は、セキュリティ オペレーターのタスクと次のタスクを実行できます。 <br/>- セキュリティ関連のポリシーを監視する <br/>- セキュリティの脅威とアラートを管理する <br/>- レポートの表示 |
| セキュリティ オペレーター | セキュリティオペレーターは、セキュリティ リーダー タスクと次のタスクを実行できます。 <br/>- 検出された脅威に関する情報を表示する <br/>- 検出された脅威を調査して対応する  |
| セキュリティ閲覧者 | セキュリティ リーダーは、次のタスクを実行できます。 <br/>- セキュリティ関連のポリシーを複数のサービスMicrosoft 365する <br/>- セキュリティの脅威とアラートを表示する <br/>- レポートの表示  |


> [!TIP]
> 管理者の役割の詳細については、「管理者Azure Active Directory管理者以外の役割をユーザーに割り当てる」を[参照](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)Azure Active Directory。 また、Defender for Endpoint の役割の詳細については、「役割ベースの [アクセス制御」を参照してください](prepare-deployment.md#role-based-access-control)。

## <a name="onboard-to-defender-for-endpoint"></a>Defender for Endpoint へのオンボード

組織のエンドポイントをオンボードする準備ができたら、次の表に示すいくつかの方法から選択できます。 <br/><br/>

|エンドポイント オペレーティング システム | オンボーディングメソッド|
|---|---|
| Windows 10 | [ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md) <br>  [グループ ポリシー](configure-endpoints-gp.md) <br>  [Microsoft エンドポイント マネージャー/ モバイル デバイス マネージャー](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI スクリプト](configure-endpoints-vdi.md)  |
| macOS | [ローカル スクリプト](mac-install-manually.md) <br> [Microsoft エンドポイント マネージャー](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [モバイル デバイス管理](mac-install-with-other-mdm.md) |
| iOS |[アプリベース](ios-install.md) |
| Android | [Microsoft エンドポイント マネージャー](android-intune.md) |

次に、次世代の保護と攻撃表面の縮小機能の構成に進みます。

## <a name="configure-next-generation-protection"></a>次世代の保護を構成する

次の図に[Microsoft エンドポイント マネージャー](/mem)、組織のデバイスとセキュリティ設定を管理するには、次の手順を使用することをお勧めします。
 
:::image type="content" source="../../media/mde-p1/endpoint-policies.png" alt-text="MEM のエンドポイント セキュリティ ポリシー":::

次の手順に従って、Microsoft エンドポイント マネージャー保護を構成します。

1. 管理センター () Microsoft エンドポイント マネージャーに移動し[https://endpoint.microsoft.com](https://endpoint.microsoft.com)、サインインします。

2. [ **Endpoint securityAntivirus** > **] を** 選択し、既存のポリシーを選択します。 (既存のポリシーを持ってない場合は、新しいポリシーを作成します)。

3. ウイルス対策の構成設定を設定または変更します。 サポートが必要な場合 次のリソースを参照してください。 <br/>

   - [設定のWindows 10 Microsoft Defender ウイルス対策ポリシーのMicrosoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)
   - [iOS の機能でエンドポイント用 Defender を構成する](ios-configure-features.md)

4. 設定の指定が完了したら、[確認] + [保存 **] を選択します**。

## <a name="configure-your-attack-surface-reduction-capabilities"></a>攻撃表面の縮小機能を構成する

攻撃表面の縮小とは、組織が攻撃を受け入可能な場所と方法を減らすことです。 Defender for Endpoint Plan 1 には、エンドポイント全体の攻撃表面を減らすのに役立ついくつかの機能が含まれています。 これらの機能を次の表に示します。 <br/><br/>

| 機能/機能 | 説明 |
|:---|:---|
| [攻撃面の減少ルール](#attack-surface-reduction-rules) | 攻撃表面の縮小ルールを構成して、ソフトウェア ベースのリスクの高い動作を制限し、組織を安全に保ちます。 攻撃表面の縮小ルールは、次のような特定のソフトウェア動作を対象とします。<br/>- ファイルのダウンロードまたは実行を試みる実行可能ファイルとスクリプトの起動 <br/>- 難読化されたスクリプトまたはその他の疑わしいスクリプトを実行する <br/>- 通常の毎日の作業中にアプリが通常開始しない動作を実行する <br/><br/>このようなソフトウェアの動作は、正当なアプリケーションで見られる場合があります。 ただし、これらの動作は、マルウェアを介して攻撃者によって悪用されるのが一般的なので、リスクが高いと見なされる場合が多い。  |
| [ランサムウェアの軽減](#ransomware-mitigation) | フォルダー アクセスの制御を構成してランサムウェアの軽減を設定し、組織の貴重なデータを悪意のあるアプリやランサムウェアなどの脅威から保護します。 | 
| [デバイス コントロール](#device-control) | 組織のデバイス制御設定を構成して、リムーバブル デバイス (USB ドライブなど) を許可またはブロックします。 | 
| [ネットワーク保護](#network-protection) | 組織内のユーザーがインターネット上の危険なドメインや悪意のあるコンテンツにアクセスするアプリケーションを使用しなかねないネットワーク保護を設定します。 |
| [Web 保護](#web-protection) | フィッシング サイト、悪用サイト、その他の信頼されていないサイトや低評価サイトから組織のデバイスを保護するための Web 脅威保護を設定します。 Web コンテンツ フィルターを設定して、コンテンツ カテゴリ (レジャー、高帯域幅、アダルト コンテンツ、法的責任など) に基づいて Web サイトへのアクセスを追跡および調整します。 |
| [ネットワーク ファイアウォール](#network-firewall) | 組織のデバイスに対するネットワーク トラフィックの入出を許可するルールを使用して、ネットワーク ファイアウォールを構成します。 |
| [アプリケーション制御](#application-control)  | 信頼できるアプリケーションとプロセスのみをデバイス上で実行する場合は、アプリケーション制御ルールをWindowsします。    |

### <a name="attack-surface-reduction-rules"></a>攻撃面の減少ルール

攻撃表面の縮小ルールは、攻撃を実行しているデバイスWindows。 次の図に示すようにMicrosoft エンドポイント マネージャーを使用することをお勧めします。

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="攻撃表面の縮小ルール (Microsoft エンドポイント マネージャー":::

1. 管理センター () Microsoft エンドポイント マネージャーに移動し[https://endpoint.microsoft.com](https://endpoint.microsoft.com)、サインインします。

2. [**Endpoint securityAttack** >  **surface reduction** > **+ Create policy] を選択します**。

3. **[プラットフォーム]** には、**[Windows 10 以降]** を選択します。

4. [ **プロファイル] で**、[ **攻撃表面の縮小ルール] を選択** し、[作成] を **選択します**。

5. [基本 **] タブで** 、ポリシーの名前と説明を指定し、[次へ] を選択 **します**。

6. [構成設定 **] タブで** 、[攻撃表面 **縮小ルール] を展開します**。

7. 各ルールの設定を指定し、[次へ] を **選択します**。 (各ルールの動作の詳細については、「攻撃表面の縮小 [ルール」を参照](attack-surface-reduction.md)してください)。 

8. [スコープ **タグ] タブ** で、組織でスコープ タグを使用している場合は、[+ スコープ タグの選択] を選択し、使用するタグを選択します。 次に、[次へ] を **選択します**。 
   
   スコープ タグの詳細については、「役割ベースのアクセス制御 (RBAC) を使用する」と「 [分散 IT のスコープ タグを使用する」を参照してください](/mem/intune/fundamentals/scope-tags)。

9. [割 **り当て]** タブで、ポリシーを適用するユーザーとグループを指定し、[次へ] を選択 **します**。 (割り当ての詳細については、「Assign [user and device profiles in Microsoft Intune」を](/mem/intune/configuration/device-profile-assign)参照してください。

10. [確認 **と作成] タブで** 設定を確認し、[作成] を選択 **します**。

> [!TIP]
> 攻撃表面の縮小ルールの詳細については、次のリソースを参照してください。
> - [マルウェア感染を防ぐために攻撃面の減少ルールを使用する](attack-surface-reduction.md)
> - [攻撃表面の縮小ルールの一覧を表示する](attack-surface-reduction-rules-reference.md)
> - [攻撃表面の縮小ルールの展開手順 3: ASR ルールの実装](attack-surface-reduction-rules-deployment-implement.md)

### <a name="ransomware-mitigation"></a>ランサムウェアの軽減

フォルダー アクセスを [制御することでランサムウェア](controlled-folders.md#what-is-controlled-folder-access)の軽減を受け取り、信頼できるアプリだけがエンドポイント上の保護されたフォルダーにアクセスできます。 

管理フォルダー アクセスを構成Microsoft エンドポイント マネージャーを使用することをお勧めします。

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="ASR ポリシー (Microsoft エンドポイント マネージャー":::

1. 管理センター () Microsoft エンドポイント マネージャーに移動し[https://endpoint.microsoft.com](https://endpoint.microsoft.com)、サインインします。 

2. [ **エンドポイント セキュリティ] を** 選択し、[攻撃表面 **の縮小] を選択します**。

3. [ **+ ポリシーの作成] を選択します**。 

4. [**プラットフォーム]** で、[Windows 10 **] を選択** し、[**プロファイル**] で [攻撃表面の縮小ルール **] を選択します**。 次に [ **作成**] を選びます。 

5. [基本 **] タブで** 、ポリシーに名前を付け、説明を追加します。 **[次へ]** を選択します。 

6. [構成設定 **] タブ** の [攻撃 **表面** 縮小ルール] セクションで、下にスクロールします。 [フォルダー保護 **を有効にする]** ドロップダウンで、[有効にする] を **選択します**。 必要に応じて、次の設定を指定できます。

   - [保護 **する必要がある追加の** フォルダーの一覧] の横にあるドロップダウン メニューを選択し、保護する必要があるフォルダーを追加します。
   - [保護 **されたフォルダーに** アクセスできるアプリの一覧] の横にあるドロップダウン メニューを選択し、保護されたフォルダーにアクセスできるアプリを追加します。
   - [攻撃 **表面の** 縮小ルールからファイルとパスを除外する] の横にあるドロップダウン メニューを選択し、攻撃表面の縮小ルールから除外する必要があるファイルとパスを追加します。

   **[次へ]** を選択します。

7. [スコープ **タグ] タブ** で、組織でスコープ タグを使用している場合は、[+ スコープ タグの選択] を選択し、使用するタグを選択します。 次に、[次へ] を **選択します**。 
   
   スコープ タグの詳細については、「役割ベースのアクセス制御 (RBAC) を使用する」と「 [分散 IT のスコープ タグを使用する」を参照してください](/mem/intune/fundamentals/scope-tags)。

8. [割り **当て] タブ** で、[すべての **ユーザーの追加]** と **[+ すべてのデバイスの** 追加] の順に選択し、[次へ] を **選択します**。 (ユーザーまたはデバイスの特定のグループを別の方法で指定できます)。

9. [確認 **と作成] タブ** で、ポリシーの設定を確認し、[作成] を選択 **します**。 ポリシーは、Defender for Endpoint にオンボードされたエンドポイントにまもなく適用されます。

### <a name="device-control"></a>デバイス コントロール

Defender for Endpoint を構成して、リムーバブル デバイス上のリムーバブル デバイスとファイルをブロックまたは許可できます。 デバイスコントロールの設定Microsoft エンドポイント マネージャーを使用することをお勧めします。

:::image type="content" source="../../media/mde-p1/mem-admintemplates.png" alt-text="Microsoft エンドポイント マネージャー管理用テンプレート":::

1. 管理センター () Microsoft エンドポイント マネージャーに移動し[https://endpoint.microsoft.com](https://endpoint.microsoft.com)、サインインします。 

2. **[デバイス]** > **[構成プロファイル]** > **[プロファイルの作成]** の順に選択します。

3. [**プラットフォーム] で**、[Windows 10 **] を選択** し、[プロファイルの **種類] で** [テンプレート] **を選択します**。 

   [ **テンプレート名] で**、[管理 **用テンプレート] を選択** し、[作成] を **選択します**。 

4. [基本 **] タブで** 、ポリシーに名前を付け、説明を追加します。 **[次へ]** を選択します。 

5. [構成設定 **] タブで**、[すべての設定 **] を設定**。 次に、検索ボックスに「リムーバブル `Removable` デバイスに関連するすべての設定を表示する」と入力します。

6. リスト内のアイテムを選択します([すべてのリムーバブル デバイス クラス] Storage: [すべてのアクセスを拒否する] など、そのアイテムを選択して、そのフライ **アウト** ウィンドウを開きます。 各設定のフライアウトは、有効、無効、または構成されていないときに何が起こるかを説明します。 設定を選択し、[OK] を **選択します**。 

7. 構成する設定ごとに手順 6 を繰り返します。 **[次へ]** を選択します。

8. [スコープ **タグ] タブ** で、組織でスコープ タグを使用している場合は、[+ スコープ タグの選択] を選択し、使用するタグを選択します。 次に、[次へ] を **選択します**。 
   
   スコープ タグの詳細については、「役割ベースのアクセス制御 (RBAC) を使用する」と「 [分散 IT のスコープ タグを使用する」を参照してください](/mem/intune/fundamentals/scope-tags)。

9. [割り **当て] タブ** で、[すべての **ユーザーの追加]** と **[+ すべてのデバイスの** 追加] の順に選択し、[次へ] を **選択します**。 (ユーザーまたはデバイスの特定のグループを別の方法で指定できます)。

10. [確認 **と作成] タブ** で、ポリシーの設定を確認し、[作成] を選択 **します**。 ポリシーは、Defender for Endpoint にオンボードされたエンドポイントにまもなく適用されます。

> [!TIP]
> 詳細については、「 [Microsoft Defender for Endpoint を使用して USB](control-usb-devices-using-intune.md) デバイスや他のリムーバブル メディアを制御する方法」を参照してください。

### <a name="network-protection"></a>ネットワーク保護

ネットワーク保護を使用すると、フィッシング詐欺、悪用、およびインターネット上の他の悪意のあるコンテンツをホストする可能性のある危険なドメインから組織を保護できます。 ネットワーク保護を有効Microsoft エンドポイント マネージャーを使用することをお勧めします。

:::image type="content" source="../../media/mde-p1/mem-endpointprotectionprofile.png" alt-text="エンドポイント保護プロファイル (Microsoft エンドポイント マネージャー":::

1. 管理センター () Microsoft エンドポイント マネージャーに移動し[https://endpoint.microsoft.com](https://endpoint.microsoft.com)、サインインします。 

2. **[デバイス]** > **[構成プロファイル]** > **[プロファイルの作成]** の順に選択します。

3. [**プラットフォーム] で**、[Windows 10 **] を選択** し、[プロファイルの **種類] で** [テンプレート] **を選択します**。 

   [ **テンプレート名] で**、[ **エンドポイント保護] を選択** し、[作成] を **選択します**。 

4. [基本 **] タブで** 、ポリシーに名前を付け、説明を追加します。 **[次へ]** を選択します。 

5. [構成の **設定] タブ** で **、[ネットワーク フィルター** Microsoft Defender Exploit Guard] を **展開します**。

   [ネットワーク **保護] を [有効]** **に設定します**。 ([監査] を選択 **して** 、最初の環境でのネットワーク保護の動作を確認できます)。

   **[次へ]** を選択します。

6. [割り **当て] タブ** で、[すべての **ユーザーの追加]** と **[+ すべてのデバイスの** 追加] の順に選択し、[次へ] を **選択します**。 (ユーザーまたはデバイスの特定のグループを別の方法で指定できます)。

7. [適用 **ルール] タブ** で、ルールを設定します。 構成するプロファイルは、指定した条件を満たすデバイスにのみ適用されます。 

   たとえば、特定の OS エディションのみを実行しているエンドポイントにポリシーを割り当てる場合があります。

   **[次へ]** を選択します。 

8. [確認 **と作成] タブ** で、ポリシーの設定を確認し、[作成] を選択 **します**。 ポリシーは、Defender for Endpoint にオンボードされたエンドポイントにまもなく適用されます。

> [!TIP]
> ネットワーク保護を有効にするには、Windows PowerShellグループ ポリシーなどの他の方法を使用できます。 詳細については、「ネットワーク保護を [有効にする」を参照してください](enable-network-protection.md)。

### <a name="web-protection"></a>Web 保護

Web 保護を使用すると、Web の脅威や望ましくないコンテンツから組織のデバイスを保護できます。 Web 保護には、 [Web 脅威保護と](#configure-web-threat-protection) [Web コンテンツ フィルターが含まれます](#configure-web-content-filtering)。 両方の機能セットを構成します。 Web 保護設定を構成Microsoft エンドポイント マネージャーを使用することをお勧めします。

#### <a name="configure-web-threat-protection"></a>Web 脅威保護の構成

1. 管理センター () Microsoft エンドポイント マネージャーに移動し[https://endpoint.microsoft.com](https://endpoint.microsoft.com)、サインインします。
 
2. [**Endpoint securityAttack** >  **surface reduction] を選択** し、[+ **ポリシーの作成] を選択します**。

3. プラットフォームを選択します(Windows 10 **など)**、Web 保護プロファイルを選択し、[**作成**] を選択 **します**。 

4. [基本] **タブで** 、名前と説明を指定し、[次へ] を選択 **します**。

5. [構成設定 **] タブで** 、[ **Web Protection**] を展開し、次の表で設定を指定し、[次へ] を選択 **します**。 <br/><br/>

   | Setting | 推奨事項 |
   |:---|:---|
   | **ネットワーク保護を有効にする** | [有効] に **設定します**。 ユーザーが悪意のあるサイトやドメインにアクセスできない。 <br/><br/>または、ネットワーク保護を監査モード **に設定** して、環境での動作を確認することもできます。 監査モードでは、ネットワーク保護によってユーザーがサイトやドメインにアクセスできませんが、検出はイベントとして追跡されます。 |
   | **ユーザーに SmartScreen を要求Microsoft Edge 従来版** | [はい] **に設定します**。 潜在的なフィッシング詐欺や悪意のあるソフトウェアからユーザーを保護するのに役立ちます。 |
   | **悪意のあるサイト へのアクセスをブロックする** | [はい] **に設定します**。 悪意のある可能性のあるサイトに関する警告をユーザーがバイパスするのを防ぐ。 |
   | **未確認ファイルのダウンロードをブロックする** | [はい] **に設定します**。 ユーザーが警告をバイパスし、未確認のファイルをダウンロードするのを防ぐ。 |

6. [スコープ **タグ] タブ** で、組織でスコープ タグを使用している場合は、[+ スコープ タグの選択] を選択し、使用するタグを選択します。 次に、[次へ] を **選択します**。 
   
   スコープ タグの詳細については、「役割ベースのアクセス制御 (RBAC) を使用する」と「 [分散 IT のスコープ タグを使用する」を参照してください](/mem/intune/fundamentals/scope-tags)。

7. [割 **り当て] タブ** で、Web 保護ポリシーを受信するユーザーとデバイスを指定し、[次へ] を選択 **します**。

8. [確認 **と作成] タブで** 、ポリシー設定を確認し、[作成] を選択 **します**。

> [!TIP]
> Web 脅威保護の詳細については、「組織を Web 脅威 [から保護する」を参照してください](web-threat-protection.md)。

#### <a name="configure-web-content-filtering"></a>Web コンテンツ フィルターの構成

1. ポータル () にMicrosoft 365 Defenderサインイン[https://security.microsoft.com/](https://security.microsoft.com/)します。

2. [**設定** > **Endpoints] を選択します**。

3. [ **ルール] で**、[ **Web コンテンツ フィルター] を選択** し、[+ ポリシーの追加 **] を選択します**。

4. [ポリシーの **追加] フライ** アウトの [全般] **タブで、** ポリシーの名前を指定し、[次へ] を選択 **します**。

5. [ブロックされた **カテゴリ] で**、ブロックする 1 つ以上のカテゴリを選択し、[次へ] を選択 **します**。

6. [スコープ **] タブ** で、このポリシーを受け取るデバイス グループを選択し、[次へ] を選択 **します**。

7. [概要 **] タブで** 、ポリシー設定を確認し、[保存] を選択 **します**。

> [!TIP]
> Web コンテンツ フィルターの構成の詳細については、「Web コンテンツ フィルター [」を参照してください](web-content-filtering.md)。

### <a name="network-firewall"></a>ネットワーク ファイアウォール

ネットワーク ファイアウォールは、ネットワーク セキュリティの脅威のリスクを軽減するのに役立ちます。 セキュリティ チームは、組織のデバイスとの間でフローを許可するトラフィックを決定するルールを設定できます。 ネットワーク ファイアウォールを構成するにはMicrosoft エンドポイント マネージャーを使用することをお勧めします。 

:::image type="content" source="../../media/mde-p1/mem-firewallpolicy.png" alt-text="ファイアウォール ポリシー (Microsoft エンドポイント マネージャー":::

基本的なファイアウォール設定を構成するには、次の手順を実行します。

1. 管理センター () Microsoft エンドポイント マネージャーに移動し[https://endpoint.microsoft.com](https://endpoint.microsoft.com)、サインインします。

2. [ **Endpoint securityFirewall** > **] を** 選択し、[+ ポリシーの作成 **] を選択します**。

3. プラットフォームを選択します(Windows 10 **など**)、**Microsoft Defender Firewall** プロファイルを選択してから、[作成] を選択 **します**。 

4. [基本] **タブで** 、名前と説明を指定し、[次へ] を選択 **します**。

5. **[Microsoft Defender Firewall] を** 展開し、リストの一番下までスクロールします。

6. 次の各設定を [はい] に **設定します**。

   - **ドメイン ネットワークの Microsoft Defender ファイアウォールを有効にする** 
   - **プライベート ネットワークの Microsoft Defender ファイアウォールを有効にする**
   - **パブリック ネットワークの Microsoft Defender ファイアウォールを有効にする**
   
   各ドメイン ネットワーク、プライベート ネットワーク、およびパブリック ネットワークの設定の一覧を確認します。 これらの設定は [構成されていません] **のままに** するか、組織のニーズに合わせて変更できます。

   **[次へ]** を選択します。

7. [スコープ **タグ] タブ** で、組織でスコープ タグを使用している場合は、[+ スコープ タグの選択] を選択し、使用するタグを選択します。 次に、[次へ] を **選択します**。 
   
   スコープ タグの詳細については、「役割ベースのアクセス制御 (RBAC) を使用する」と「 [分散 IT のスコープ タグを使用する」を参照してください](/mem/intune/fundamentals/scope-tags)。

8. [割り **当て] タブ** で、[すべての **ユーザーの追加]** と **[+ すべてのデバイスの** 追加] の順に選択し、[次へ] を **選択します**。 (ユーザーまたはデバイスの特定のグループを別の方法で指定できます)。

9. [確認 **と作成] タブで** 、ポリシー設定を確認し、[作成] を選択 **します**。

> [!TIP]
> ファイアウォールの設定は詳細で、複雑に見える場合があります。 「ファイアウォール[を構成するためのベスト プラクティスWindows Defender参照してください](/windows/security/threat-protection/windows-firewall/best-practices-configuring)。

### <a name="application-control"></a>アプリケーション制御

Windows Defenderアプリケーション制御 (WDAC) は、信頼Windowsアプリケーションとプロセスの実行のみを許可することで、エンドポイントを保護するのに役立ちます。 ほとんどの組織では、WDAC の段階的な展開を使用しました。 つまり、ほとんどの組織では、最初は、すべてのエンドポイントで WDAC Windows展開する必要があります。 実際、組織の Windows エンドポイントが完全に管理されている、軽く管理されている、または "自分のデバイスを持ち込む" エンドポイントかどうかに応じて、すべてのエンドポイントまたは一部のエンドポイントに WDAC を展開できます。

WDAC 展開の計画に役立つ情報については、次のリソースを参照してください。

- [Windows 向けアプリケーション制御](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Windows Defenderコントロール ポリシーの設計上の決定](/windows/security/threat-protection/windows-defender-application-control/understand-windows-defender-application-control-policy-design-decisions)

- [Windows Defenderシナリオでのアプリケーション制御の展開:デバイスの種類](/windows/security/threat-protection/windows-defender-application-control/types-of-devices)

## <a name="next-steps"></a>次のステップ

セットアップと構成プロセスが完了したので、次に、Defender for Endpoint の使用を開始します。 

- [Defender for Endpoint Plan 1 の概要](mde-plan1-getting-started.md)
