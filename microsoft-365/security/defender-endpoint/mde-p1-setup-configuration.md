---
title: プラン 1 のセットアップと構成Microsoft Defender for Endpoint
description: Defender for Endpoint Plan 1 を設定して構成する方法について説明します。 要件を確認し、ロールアウトを計画し、環境を設定します。
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
ms.openlocfilehash: 774139aa6ccbf0562d5f6a9bf14eb89550e865a8
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665956"
---
# <a name="set-up-and-configure-microsoft-defender-for-endpoint-plan-1"></a>プラン 1 のセットアップと構成Microsoft Defender for Endpoint

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

この記事では、Defender for Endpoint Plan 1 を設定して構成する方法について説明します。 サポートを受ける場合でも、自分で行っている場合でも、この記事をデプロイ全体のガイドとして使用できます。  

## <a name="the-setup-and-configuration-process"></a>セットアップと構成プロセス

:::image type="content" source="images/mde-p1-deploymentflow.png" alt-text="Microsoft Defender for Endpoint プラン 1 のセットアップと展開のフロー" lightbox="images/mde-p1-deploymentflow.png":::

Defender for Endpoint Plan 1 の一般的なセットアップと構成プロセスは次のとおりです。 <br/><br/>


| 番号  | 手順  | 説明  |
|:---------:|:---------|:---------|
| 1 | [要件を確認する](#review-the-requirements)  | ライセンス、ブラウザー、オペレーティング システム、データセンターの要件を一覧表示します   |
| 2 | [展開の計画](#plan-your-deployment) | 考慮すべきデプロイ方法をいくつか一覧表示し、使用する方法を決定するのに役立つその他のリソースへのリンクを含めます  |
| 3 | [テナント環境を設定する](#set-up-your-tenant-environment) | テナント環境を設定するためのタスクの一覧 |
| 4 | [ロールとアクセス許可を割り当てる](#assign-roles-and-permissions) | セキュリティ チームで考慮すべきロールとアクセス許可を一覧表示します <br/><br/>**ヒント**: ロールとアクセス許可が割り当てられるとすぐに、セキュリティ チームはMicrosoft 365 Defender ポータルの使用を開始できます。 詳細については、「 [作業の開始」](mde-plan1-getting-started.md)を参照してください。 |
| 5 | [Defender for Endpoint へのオンボード](#onboard-to-defender-for-endpoint) | Defender for Endpoint Plan 1 にオンボードするオペレーティング システム別のいくつかのメソッドの一覧と、各メソッドの詳細な情報へのリンクが含まれています  |
| 6  | [次世代の保護を構成する](#configure-next-generation-protection) | Microsoft エンドポイント マネージャーで次世代の保護設定を構成する方法について説明します  |
| 7  | [攻撃面の縮小機能を構成する](#configure-your-attack-surface-reduction-capabilities)        | 構成できる攻撃表面縮小機能の種類を一覧表示し、より多くのリソースへのリンクを含む手順を含めます  |
 
## <a name="review-the-requirements"></a>システム要件を確認する

次の表に、Defender for Endpoint プラン 1 の基本的な要件を示します。<br/><br/>

| 要件 | 説明 |
|:---|:---|
| ライセンスの要件 | Defender for Endpoint プラン 1 |
| ブラウザー要件 | Microsoft Edge <br/> Internet Explorer バージョン 11 <br/> Google Chrome |
| オペレーティング システム | Windows 10バージョン 1709 以降 <br/>macOS: 11.5 (Big Sur)、10.15.7 (Catalina)、または 10.14.6 (Mojave) <br/>iOS <br/>Android OS  |
| Datacenter | 次のいずれかのデータセンターの場所。 <br/>- 欧州連合 <br/>- イギリス <br/>- 米国 |


## <a name="plan-your-deployment"></a>展開の計画

デプロイを計画するときは、いくつかの異なるアーキテクチャとデプロイ方法から選択できます。 各組織は一意であるため、次の表に示すように、考慮すべきいくつかのオプションがあります。 <br/><br/>

| メソッド | 説明 |
|:---|:---|
| [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Microsoft エンドポイント マネージャーに含まれる) | Intuneを使用してクラウド ネイティブ環境でエンドポイントを管理する |
| [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)と[Configuration Manager](/mem/configmgr/core/understand/introduction) (Microsoft エンドポイント マネージャーに含まれる) | IntuneとConfiguration Managerを使用して、オンプレミスとクラウド環境にまたがるエンドポイントとワークロードを管理する |
| [Configuration Manager](/mem/configmgr/core/understand/introduction) | Configuration Managerを使用して、Defender for Endpoint のクラウドベースの機能を使用してオンプレミス エンドポイントを保護する |
| Microsoft 365 Defender ポータルからダウンロードしたローカル スクリプト | エンドポイントでローカル スクリプトを使用してパイロットを実行するか、少数のデバイスのみをオンボードする |

デプロイ オプションの詳細については、「 [Defender for Endpoint デプロイを計画する」を](deployment-strategy.md)参照してください。 次のポスターをダウンロードします。 

[:::image type="content" source="../../media/defender-endpoint/mde-deployment-strategy.png" alt-text="展開戦略ポスターサムネイル":::](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)

**[デプロイ ポスターを入手する](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)**

> [!TIP]
> デプロイの計画の詳細については、「[Microsoft Defender for Endpointデプロイを計画する](deployment-strategy.md)」を参照してください。

## <a name="set-up-your-tenant-environment"></a>テナント環境を設定する

テナント環境の設定には、次のようなタスクが含まれます。

- ライセンスの確認
- テナントの構成
- プロキシ設定の構成 (必要な場合のみ)
- センサーが正しく動作していることを確認し、Defender for Endpoint にデータを報告する 

これらのタスクは、Defender for Endpoint のセットアップ フェーズに含まれています。 「 [Defender for Endpoint のセットアップ」を参照してください](production-deployment.md)。

## <a name="assign-roles-and-permissions"></a>ロールとアクセス許可を割り当てる

Microsoft 365 Defender ポータルにアクセスしたり、Defender for Endpoint の設定を構成したり、検出された脅威に対して応答アクションを実行したりするなどのタスクを実行するには、適切なアクセス許可を割り当てる必要があります。 Defender for Endpoint では、[Azure Active Directory内に組み込みのロールが使用されます](/azure/active-directory/roles/permissions-reference)。 

Microsoft では、タスクを実行するために必要なアクセス許可のレベルのみをユーザーに割り当てることをお勧めします。 アクセス許可は、基本的なアクセス許可管理を使用するか、 [ロールベースのアクセス制御](rbac.md) (RBAC) を使用して割り当てることができます。 

- 基本的なアクセス許可管理では、グローバル管理者とセキュリティ管理者はフル アクセス権を持ち、セキュリティ 閲覧者は読み取り専用アクセス権を持ちます。
- RBAC を使用すると、より多くのロールを使用して、より細かいアクセス許可を設定できます。 たとえば、セキュリティ リーダー、セキュリティ オペレーター、セキュリティ管理者、エンドポイント管理者などを作成できます。


次の表では、組織内の Defender for Endpoint について考慮すべき重要な役割について説明します。 <br/><br/>

| 役割 | 説明 |
|:---|:---|
| グローバル管理者 (グローバル管理者とも呼ばれます) <br/><br/> *ベスト プラクティスとして、グローバル管理者の数を制限します。* | グローバル管理者は、あらゆる種類のタスクを実行できます。 Microsoft 365またはMicrosoft Defender for Endpointプラン 1 に会社をサインアップしたユーザーは、既定でグローバル管理者です。 <br/><br/> グローバル管理者は、次のようなすべてのMicrosoft 365 ポータルで設定にアクセス/変更できます。 <br/>- Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) <br/>- Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) <br/>- Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com))  |
| セキュリティ管理者 (セキュリティ管理者とも呼ばれます) | セキュリティ管理者は、セキュリティ オペレーター タスクと次のタスクを実行できます。 <br/>- セキュリティ関連のポリシーを監視する <br/>- セキュリティの脅威とアラートを管理する <br/>- レポートを表示する |
| セキュリティ オペレーター | セキュリティ オペレーターは、セキュリティ リーダー タスクと次のタスクを実行できます。 <br/>- 検出された脅威に関する情報を表示する <br/>- 検出された脅威を調査して対応する  |
| セキュリティ閲覧者 | セキュリティ リーダーは、次のタスクを実行できます。 <br/>- Microsoft 365 サービス間でセキュリティ関連のポリシーを表示する <br/>- セキュリティの脅威とアラートを表示する <br/>- レポートを表示する  |


> [!TIP]
> Azure Active Directoryのロールの詳細については、「Azure Active Directoryを[持つユーザーに管理者ロールと管理者以外のロールを割り当てる](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)」を参照してください。 また、Defender for Endpoint のロールの詳細については、 [ロールベースのアクセス制御に関](prepare-deployment.md#role-based-access-control)するページを参照してください。

## <a name="onboard-to-defender-for-endpoint"></a>Defender for Endpoint へのオンボード

組織のエンドポイントをオンボードする準備ができたら、次の表に示すように、いくつかの方法から選択できます。 <br/><br/>

|エンドポイント オペレーティング システム | オンボードメソッド|
|---|---|
| Windows 10 | [ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md) <br>  [グループ ポリシー](configure-endpoints-gp.md) <br>  [Microsoft エンドポイント マネージャー/ モバイル デバイス マネージャー](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI スクリプト](configure-endpoints-vdi.md)  |
| macOS | [ローカル スクリプト](mac-install-manually.md) <br> [Microsoft エンドポイント マネージャー](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [モバイル デバイス管理](mac-install-with-other-mdm.md) |
| iOS |[アプリベース](ios-install.md) |
| Android | [Microsoft エンドポイント マネージャー](android-intune.md) |

次に、次世代の保護と攻撃面の縮小機能の構成に進みます。

## <a name="configure-next-generation-protection"></a>次世代の保護を構成する

次の図に示すように、[Microsoft エンドポイント マネージャー](/mem)を使用して組織のデバイスとセキュリティ設定を管理することをお勧めします。
 
:::image type="content" source="../../media/mde-p1/endpoint-policies.png" alt-text="Micorosft エンドポイント マネージャー ポータルのエンドポイント セキュリティ ポリシー" lightbox="../../media/mde-p1/endpoint-policies.png":::

Microsoft エンドポイント マネージャーで次世代保護を構成するには、次の手順に従います。

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、サインインします。

2. **[Endpoint** **securityAntivirus** > ] を選択し、既存のポリシーを選択します。 (既存のポリシーがない場合は、新しいポリシーを作成します)。

3. ウイルス対策の構成設定を設定または変更します。 お困りの際は、 次のリソースを参照してください。 <br/>

   - [Microsoft IntuneのWindows 10 Microsoft Defender ウイルス対策 ポリシーの設定](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)
   - [iOS 機能で Defender for Endpoint を構成する](ios-configure-features.md)

4. 設定の指定が完了したら、[ **確認と保存**] を選択します。

## <a name="configure-your-attack-surface-reduction-capabilities"></a>攻撃面の縮小機能を構成する

攻撃面の縮小は、組織が攻撃を受け入れる場所と方法を減らすことです。 Defender for Endpoint Plan 1 には、エンドポイント全体の攻撃面を減らすのに役立ついくつかの機能と機能が含まれています。 これらの機能と機能を次の表に示します。 <br/><br/>

| 機能/機能 | 説明 |
|:---|:---|
| [攻撃面の減少ルール](#attack-surface-reduction-rules) | ソフトウェア ベースの危険な動作を制約し、組織を安全に保つために、攻撃面の縮小ルールを構成します。 攻撃面の縮小ルールは、次のような特定のソフトウェア動作を対象とします。<br/>- ファイルのダウンロードまたは実行を試みる実行可能ファイルとスクリプトを起動する <br/>- 難読化された、またはその他の疑わしいスクリプトの実行 <br/>- 通常の日常的な作業中にアプリが通常開始しない動作を実行する <br/><br/>このようなソフトウェア動作は、正当なアプリケーションで見られる場合があります。 ただし、これらの動作は、マルウェアを介して攻撃者によって一般的に悪用されるため、リスクが高いと見なされることがよくあります。  |
| [ランサムウェアの軽減策](#ransomware-mitigation) | フォルダー アクセスの制御を構成してランサムウェアの軽減策を設定します。これにより、悪意のあるアプリやランサムウェアなどの脅威から組織の貴重なデータを保護できます。 | 
| [デバイス コントロール](#device-control) | リムーバブル デバイス (USB ドライブなど) を許可またはブロックするように、組織のデバイス制御設定を構成します。 | 
| [ネットワーク保護](#network-protection) | 組織内のユーザーが、インターネット上の危険なドメインや悪意のあるコンテンツにアクセスするアプリケーションを使用できないように、ネットワーク保護を設定します。 |
| [Web 保護](#web-protection) | 組織のデバイスをフィッシング サイト、悪用サイト、その他の信頼されていないサイトや低評価のサイトから保護するように Web 脅威保護を設定します。 Web コンテンツ フィルターを設定して、コンテンツ カテゴリ (例: 遊び、高帯域幅、成人向けコンテンツ、法的責任) に基づいて Web サイトへのアクセスを追跡および規制します。 |
| [ネットワーク ファイアウォール](#network-firewall) | 組織のデバイスへの出入りが許可されているネットワーク トラフィックを決定するルールを使用して、ネットワーク ファイアウォールを構成します。 |
| [アプリケーション制御](#application-control)  | 信頼されたアプリケーションとプロセスのみをWindows デバイスで実行できるようにする場合は、アプリケーション制御ルールを構成します。    |

### <a name="attack-surface-reduction-rules"></a>攻撃面の減少ルール

攻撃対象の縮小ルールは、Windowsを実行しているデバイスで使用できます。 次の図に示すように、Microsoft エンドポイント マネージャーを使用することをお勧めします。

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="Microsoft エンドポイント マネージャー ポータルでの攻撃面の縮小ルール" lightbox="../../media/mde-p1/mem-asrpolicies.png":::

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、サインインします。

2. [Endpoint **securityAttack surface reduction+** Create policy] (**Endpoint securityAttack** >  surface reduction > **+ Create policy**) を選択します。

3. **[プラットフォーム]** には、**[Windows 10 以降]** を選択します。

4. **[プロファイル]** で [**攻撃面の縮小ルール**] を選択し、[**作成**] を選択します。

5. [ **基本]** タブで、ポリシーの名前と説明を指定し、[ **次へ**] を選択します。

6. [ **構成の設定]** タブで、[ **攻撃面の縮小ルール**] を展開します。

7. 各ルールの設定を指定し、[ **次へ**] を選択します。 (各ルールの動作の詳細については、 [攻撃面の縮小ルール](attack-surface-reduction.md)に関するページを参照してください)。 

8. [ **スコープ タグ** ] タブで、組織でスコープ タグを使用している場合は、[ **+ スコープ タグの選択]** を選択し、使用するタグを選択します。 次に、[ **次へ**] を選択します。 
   
   スコープ タグの詳細については、「 [分散 IT にロールベースのアクセス制御 (RBAC) とスコープ タグを使用する」を](/mem/intune/fundamentals/scope-tags)参照してください。

9. **[割り当て]** タブで、ポリシーを適用するユーザーとグループを指定し、**[次へ]** を選択します。 (割り当ての詳細については、「[Microsoft Intuneでユーザー プロファイルとデバイス プロファイルを割り当てる](/mem/intune/configuration/device-profile-assign)」を参照してください)。

10. **[確認と作成]** タブで、設定を確認し、**[作成]** を選択します。

> [!TIP]
> 攻撃表面の縮小ルールの詳細については、次のリソースを参照してください。
> - [マルウェア感染を防ぐために攻撃面の減少ルールを使用する](attack-surface-reduction.md)
> - [攻撃面の縮小ルールの一覧を表示する](attack-surface-reduction-rules-reference.md)
> - [攻撃対象の縮小規則の展開手順 3: ASR 規則を実装する](attack-surface-reduction-rules-deployment-implement.md)

### <a name="ransomware-mitigation"></a>ランサムウェアの軽減策

フォルダー [アクセスの制御](controlled-folders.md#what-is-controlled-folder-access)によってランサムウェアの軽減策が得られます。これにより、信頼されたアプリのみがエンドポイント上の保護されたフォルダーにアクセスできるようになります。 

Microsoft エンドポイント マネージャーを使用して、フォルダー アクセスの制御を構成することをお勧めします。

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="Microsoft エンドポイント マネージャー ポータルの ASR ポリシー" lightbox="../../media/mde-p1/mem-asrpolicies.png":::

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、サインインします。 

2. **[エンドポイント セキュリティ]** を選択し、[**攻撃面の縮小**] を選択します。

3. [ **+ ポリシーの作成]** を選択します。 

4. **[プラットフォーム**] **で [Windows 10以降**] を選択し、[**プロファイル**] で [**攻撃面の縮小ルール**] を選択します。 次に [ **作成**] を選びます。 

5. [ **基本]** タブで、ポリシーに名前を付け、説明を追加します。 **[次へ]** を選択します。 

6. [ **構成設定** ] タブの [ **攻撃面の縮小ルール** ] セクションで、下にスクロールします。 [ **フォルダー保護を有効にする]** ドロップダウンで、[ **有効]** を選択します。 必要に応じて、次の他の設定を指定できます。

   - [ **保護する必要があるその他のフォルダーの一覧**] の横にあるドロップダウン メニューを選択し、保護する必要があるフォルダーを追加します。
   - [ **保護されたフォルダーにアクセスできるアプリの一覧] の** 横にあるドロップダウン メニューを選択し、保護されたフォルダーにアクセスできるアプリを追加します。
   - [ **攻撃対象の縮小ルールからファイルとパスを除外** する] の横にあるドロップダウン メニューを選択し、攻撃対象の縮小ルールから除外する必要があるファイルとパスを追加します。

   **[次へ]** を選択します。

7. [ **スコープ タグ** ] タブで、組織でスコープ タグを使用している場合は、[ **+ スコープ タグの選択]** を選択し、使用するタグを選択します。 次に、[ **次へ**] を選択します。 
   
   スコープ タグの詳細については、「 [分散 IT にロールベースのアクセス制御 (RBAC) とスコープ タグを使用する」を](/mem/intune/fundamentals/scope-tags)参照してください。

8. [ **割り当て** ] タブで、[ **すべてのユーザーの追加]** と [ **+ すべてのデバイスの追加]** の順に選択し、[ **次へ**] を選択します。 (ユーザーまたはデバイスの特定のグループを別の方法で指定することもできます)。

9. [ **確認と作成** ] タブで、ポリシーの設定を確認し、[ **作成**] を選択します。 ポリシーは、まもなく Defender for Endpoint にオンボードされたすべてのエンドポイントに適用されます。

### <a name="device-control"></a>デバイス制御

Defender for Endpoint を構成して、リムーバブル デバイス上のリムーバブル デバイスとファイルをブロックまたは許可できます。 Microsoft エンドポイント マネージャーを使用して、デバイス制御設定を構成することをお勧めします。

:::image type="content" source="../../media/mde-p1/mem-admintemplates.png" alt-text="Microsoft エンドポイント マネージャー管理用テンプレート" lightbox="../../media/mde-p1/mem-admintemplates.png":::

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、サインインします。 

2. **[デバイス]** > **[構成プロファイル]** > **[プロファイルの作成]** の順に選択します。

3. **[プラットフォーム**] で **Windows 10以降** を選択し、[**プロファイルの種類**] で [テンプレート] を選択 **します**。 

   [ **テンプレート名**] で [ **管理用テンプレート**] を選択し、[ **作成**] を選択します。 

4. [ **基本]** タブで、ポリシーに名前を付け、説明を追加します。 **[次へ]** を選択します。 

5. [**構成設定**] タブで、[**すべての設定**] を選択します。 次に、検索ボックスに「」と入力 `Removable` して、リムーバブル デバイスに関連するすべての設定を表示します。

6. [**すべてのリムーバブル Storage クラス: すべてのアクセスを拒否** する] など、一覧内の項目を選択してポップアップ ウィンドウを開きます。 各設定のポップアップでは、有効、無効、または未構成の場合の動作について説明します。 設定を選択し、[OK] を選択 **します**。 

7. 構成する設定ごとに手順 6 を繰り返します。 **[次へ]** を選択します。

8. [ **スコープ タグ** ] タブで、組織でスコープ タグを使用している場合は、[ **+ スコープ タグの選択]** を選択し、使用するタグを選択します。 次に、[ **次へ**] を選択します。 
   
   スコープ タグの詳細については、「 [分散 IT にロールベースのアクセス制御 (RBAC) とスコープ タグを使用する」を](/mem/intune/fundamentals/scope-tags)参照してください。

9. [ **割り当て** ] タブで、[ **すべてのユーザーの追加]** と [ **+ すべてのデバイスの追加]** の順に選択し、[ **次へ**] を選択します。 (ユーザーまたはデバイスの特定のグループを別の方法で指定することもできます)。

10. [ **確認と作成** ] タブで、ポリシーの設定を確認し、[ **作成**] を選択します。 ポリシーは、まもなく Defender for Endpoint にオンボードされたすべてのエンドポイントに適用されます。

> [!TIP]
> 詳細については、「[Microsoft Defender for Endpointを使用して USB デバイスやその他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)」を参照してください。

### <a name="network-protection"></a>ネットワーク保護

ネットワーク保護を使用すると、フィッシング詐欺、悪用、その他の悪意のあるコンテンツをインターネット上でホストする可能性のある危険なドメインから組織を保護するのに役立ちます。 Microsoft エンドポイント マネージャーを使用してネットワーク保護を有効にすることをお勧めします。

:::image type="content" source="../../media/mde-p1/mem-endpointprotectionprofile.png" alt-text="Microsoft エンドポイント マネージャー ポータルのエンドポイント保護プロファイル" lightbox="../../media/mde-p1/mem-endpointprotectionprofile.png":::

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、サインインします。 

2. **[デバイス]** > **[構成プロファイル]** > **[プロファイルの作成]** の順に選択します。

3. **[プラットフォーム**] で **Windows 10以降** を選択し、[**プロファイルの種類**] で [テンプレート] を選択 **します**。 

   [ **テンプレート名**] で [ **エンドポイント保護**] を選択し、[ **作成**] を選択します。 

4. [ **基本]** タブで、ポリシーに名前を付け、説明を追加します。 **[次へ]** を選択します。 

5. [**構成設定**] タブで、[**Microsoft Defender Exploit Guard**] を展開し、[**ネットワーク フィルター]** を展開します。

   **[ネットワーク保護**] を **[有効]** に設定します。 ([ **監査** ] を選択して、最初に環境でネットワーク保護がどのように機能するかを確認することもできます)。

   **[次へ]** を選択します。

6. [ **割り当て** ] タブで、[ **すべてのユーザーの追加]** と [ **+ すべてのデバイスの追加]** の順に選択し、[ **次へ**] を選択します。 (ユーザーまたはデバイスの特定のグループを別の方法で指定することもできます)。

7. [ **適用規則** ] タブで、ルールを設定します。 構成するプロファイルは、指定した組み合わされた条件を満たすデバイスにのみ適用されます。 

   たとえば、特定の OS エディションのみを実行しているエンドポイントにポリシーを割り当てることを選択できます。

   **[次へ]** を選択します。 

8. [ **確認と作成** ] タブで、ポリシーの設定を確認し、[ **作成**] を選択します。 ポリシーは、まもなく Defender for Endpoint にオンボードされたすべてのエンドポイントに適用されます。

> [!TIP]
> Windows PowerShellやグループ ポリシーなどの他の方法を使用して、ネットワーク保護を有効にすることができます。 詳細については、「 [ネットワーク保護を有効にする」](enable-network-protection.md)を参照してください。

### <a name="web-protection"></a>Web 保護

Web 保護を使用すると、Web の脅威や不要なコンテンツから組織のデバイスを保護できます。 Web 保護には、 [Web 脅威の保護](#configure-web-threat-protection) と [Web コンテンツのフィルター処理が](#configure-web-content-filtering)含まれます。 両方の機能セットを構成します。 Microsoft エンドポイント マネージャーを使用して、Web 保護設定を構成することをお勧めします。

#### <a name="configure-web-threat-protection"></a>Web 脅威保護を構成する

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、サインインします。
 
2. **[Endpoint securityAttack** >  **surface reduction**] を選択し、[**+ ポリシーの作成**] を選択します。

3. **Windows 10などの** プラットフォームを選択し、**Web 保護** プロファイルを選択して、[**作成**] を選択します。 

4. [ **基本]** タブで、名前と説明を指定し、[ **次へ**] を選択します。

5. [ **構成設定** ] タブで[ **Web Protection**] を展開し、次の表の設定を指定して、[ **次へ**] を選択します。 <br/><br/>

   | Setting | 推奨事項 |
   |:---|:---|
   | **ネットワーク保護を有効にする** | **[有効]** に設定します。 ユーザーが悪意のあるサイトまたはドメインにアクセスできないようにします。 <br/><br/>または、ネットワーク保護を **監査モード** に設定して、環境内での動作を確認することもできます。 監査モードでは、ネットワーク保護によってユーザーがサイトまたはドメインにアクセスすることは禁止されませんが、検出はイベントとして追跡されます。 |
   | **Microsoft Edge 従来版に SmartScreen を必要とする** | **[はい**] に設定します。 潜在的なフィッシング詐欺や悪意のあるソフトウェアからユーザーを保護するのに役立ちます。 |
   | **悪意のあるサイト へのアクセスをブロックする** | **[はい**] に設定します。 ユーザーが悪意のある可能性のあるサイトに関する警告をバイパスできないようにします。 |
   | **未検証ファイルのダウンロードをブロックする** | **[はい**] に設定します。 ユーザーが警告をバイパスし、未検証ファイルをダウンロードできないようにします。 |

6. [ **スコープ タグ** ] タブで、組織でスコープ タグを使用している場合は、[ **+ スコープ タグの選択]** を選択し、使用するタグを選択します。 次に、[ **次へ**] を選択します。 
   
   スコープ タグの詳細については、「 [分散 IT にロールベースのアクセス制御 (RBAC) とスコープ タグを使用する」を](/mem/intune/fundamentals/scope-tags)参照してください。

7. [ **割り当て** ] タブで、Web 保護ポリシーを受け取るユーザーとデバイスを指定し、[ **次へ**] を選択します。

8. [ **確認と作成** ] タブで、ポリシー設定を確認し、[ **作成**] を選択します。

> [!TIP]
> Web 脅威保護の詳細については、「Web 脅威 [から組織を保護する](web-threat-protection.md)」を参照してください。

#### <a name="configure-web-content-filtering"></a>Web コンテンツ フィルターを構成する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com/](https://security.microsoft.com/)) に移動してサインインします。

2. **設定** > **Endpoints を選択します**。

3. [ **ルール]** で [ **Web コンテンツ フィルター**] を選択し、[ **+ ポリシーの追加]** を選択します。

4. [ **ポリシーの追加]** ポップアップの [ **全般** ] タブで、ポリシーの名前を指定し、[ **次へ**] を選択します。

5. **[ブロック] カテゴリ** で、ブロックする 1 つ以上のカテゴリを選択し、[**次へ**] を選択します。

6. [ **スコープ** ] タブで、このポリシーを受け取るデバイス グループを選択し、[ **次へ**] を選択します。

7. [概要] タブ **で** 、ポリシー設定を確認し、[ **保存]** を選択します。

> [!TIP]
> Web コンテンツ フィルターの構成の詳細については、「 [Web コンテンツ のフィルター処理](web-content-filtering.md)」を参照してください。

### <a name="network-firewall"></a>ネットワーク ファイアウォール

ネットワーク ファイアウォールは、ネットワーク セキュリティの脅威のリスクを軽減するのに役立ちます。 セキュリティ チームは、組織のデバイスとの間のフローが許可されているトラフィックを決定するルールを設定できます。 Microsoft エンドポイント マネージャーを使用してネットワーク ファイアウォールを構成することをお勧めします。 

:::image type="content" source="../../media/mde-p1/mem-firewallpolicy.png" alt-text="Microsoft エンドポイント マネージャー ポータルのファイアウォール ポリシー" lightbox="../../media/mde-p1/mem-firewallpolicy.png":::

ファイアウォールの基本設定を構成するには、次の手順に従います。

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、サインインします。

2. **[Endpoint** **securityFirewall** > ] を選択し、[**+ ポリシーの作成**] を選択します。

3. **Windows 10などの** プラットフォームを選択し、**Microsoft Defender ファイアウォール** プロファイルを選択して、[**作成**] を選択します。 

4. [ **基本]** タブで、名前と説明を指定し、[ **次へ**] を選択します。

5. **Microsoft Defender Firewall** を展開し、一覧の一番下まで下にスクロールします。

6. 次の各設定を **[はい**] に設定します。

   - **ドメイン ネットワークに対して Microsoft Defender Firewall を有効にする** 
   - **プライベート ネットワーク用の Microsoft Defender ファイアウォールを有効にする**
   - **パブリック ネットワークに対して Microsoft Defender Firewall を有効にする**
   
   各ドメイン ネットワーク、プライベート ネットワーク、パブリック ネットワークの下にある設定の一覧を確認します。 [ **未構成]** に設定したままにすることも、組織のニーズに合わせて変更することもできます。

   **[次へ]** を選択します。

7. [ **スコープ タグ** ] タブで、組織でスコープ タグを使用している場合は、[ **+ スコープ タグの選択]** を選択し、使用するタグを選択します。 次に、[ **次へ**] を選択します。 
   
   スコープ タグの詳細については、「 [分散 IT にロールベースのアクセス制御 (RBAC) とスコープ タグを使用する」を](/mem/intune/fundamentals/scope-tags)参照してください。

8. [ **割り当て** ] タブで、[ **すべてのユーザーの追加]** と [ **+ すべてのデバイスの追加]** の順に選択し、[ **次へ**] を選択します。 (ユーザーまたはデバイスの特定のグループを別の方法で指定することもできます)。

9. [ **確認と作成** ] タブで、ポリシー設定を確認し、[ **作成**] を選択します。

> [!TIP]
> ファイアウォールの設定は詳細であり、複雑に見える場合があります。 ファイアウォールを[構成するためのベスト プラクティスWindows Defender](/windows/security/threat-protection/windows-firewall/best-practices-configuring)参照してください。

### <a name="application-control"></a>アプリケーション制御

Windows Defender アプリケーション制御 (WDAC) は、信頼されたアプリケーションとプロセスの実行のみを許可することで、Windows エンドポイントを保護するのに役立ちます。 ほとんどの組織では、WDAC の段階的な展開が使用されました。 つまり、ほとんどの組織は、最初にすべてのWindows エンドポイントに WDAC を展開しません。 実際、組織のWindows エンドポイントが完全に管理されているか、軽く管理されているか、または "Bring Your Own Device" エンドポイントであるかに応じて、すべてのエンドポイントまたは一部のエンドポイントに WDAC を展開できます。

WDAC 展開の計画を支援するには、次のリソースを参照してください。

- [Windows 向けアプリケーション制御](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Windows Defender アプリケーション制御ポリシーの設計に関する決定](/windows/security/threat-protection/windows-defender-application-control/understand-windows-defender-application-control-policy-design-decisions)

- [さまざまなシナリオでのアプリケーション制御の展開Windows Defender:デバイスの種類](/windows/security/threat-protection/windows-defender-application-control/types-of-devices)

## <a name="next-steps"></a>次の手順

セットアップと構成プロセスを完了したので、次の手順は Defender for Endpoint の使用を開始することです。 

- [Defender for Endpoint プラン 1 を使用した概要](mde-plan1-getting-started.md)
