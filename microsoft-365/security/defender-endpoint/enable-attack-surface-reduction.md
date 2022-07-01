---
title: 攻撃面の減少ルールを有効にする
description: マクロ、スクリプト、および一般的なインジェクション手法を使用する攻撃からデバイスを保護するために、攻撃表面縮小 (ASR) ルールを有効にします。
keywords: 攻撃面の削減, hips, ホスト侵入防止システム, 保護ルール, アンチエクスプロイト, antiexploit, Exploit, infection prevention, enable, on
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.date: 1/18/2022
ms.openlocfilehash: 90244050b9fd8e5714ba28f7ac9850091d368da7
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66601226"
---
# <a name="enable-attack-surface-reduction-rules"></a>攻撃面の減少ルールを有効にする

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

> [!TIP]
> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

[攻撃表面の縮小ルール](attack-surface-reduction.md) (ASR ルール) は、マルウェアがデバイスやネットワークを侵害するために悪用されることが多いアクションを防ぐのに役立ちます。

## <a name="requirements"></a>要件

Windows バージョン全体の攻撃面の縮小機能

次のいずれかのエディションとバージョンの Windows を実行しているデバイスに対して、攻撃面の縮小規則を設定できます。

- [Windows 11 Pro](/windows/whats-new/windows-11-overview)
- [Windows 11 Enterprise](https://www.microsoft.com/microsoft-365/windows/windows-11-enterprise)
- Windows 10 Pro[バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) 以降
- Windows 10 Enterprise[バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) 以降
- Windows Server [バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803) 以降
- [Windows Server 2012 R2](/windows/win32/srvnodes/what-s-new-for-windows-server-2012-r2)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2022](/windows-server/get-started/whats-new-in-windows-server-2022)

攻撃表面の縮小ルールの機能セット全体を使用するには、次のものが必要です。

- プライマリ AV としてのWindows Defender ウイルス対策 (リアルタイム保護オン)
- [Cloud-Delivery Protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) on (一部のルールでは必須)
- Windows 10 Enterprise E5 または E3 ライセンス

攻撃表面の縮小ルールには [Windows E5 ライセンス](/windows/deployment/deploy-enterprise-licenses)は必要ありませんが、Windows E5 ライセンスを使用すると、Defender for Endpoint で使用できる監視、分析、ワークフローなどの高度な管理機能と、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>のレポート機能と構成機能を利用できます。 これらの高度な機能は E3 ライセンスでは使用できませんが、引き続きイベント ビューアーを使用して攻撃表面縮小ルール イベントを確認できます。

各 ASR ルールには、次の 4 つの設定のいずれかが含まれています。

- **未構成** | **無効**: ASR 規則を無効にする
- **ブロック**: ASR 規則を有効にする
- **監査**: 有効にした場合に ASR ルールが組織にどのような影響を与えるかを評価する
- **警告**: ASR ルールを有効にするが、エンド ユーザーがブロックをバイパスできるようにする

Windows E5 ライセンス (または同様のライセンス SKU) で ASR ルールを使用して、[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) で利用できる高度な監視機能とレポート機能を利用することをお勧めします。 ただし、高度な監視機能とレポート機能を含まない Windows Professional や Windows E3 などの別のライセンスがある場合は、ASR ルールがトリガーされたときに各エンドポイントで生成されるイベント (イベント転送など) に基づいて独自の監視ツールとレポート ツールを開発できます。

> [!TIP]
> Windows ライセンスの詳細については、「[Windows 10 ライセンス](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5)」を参照し、[Windows 10のボリューム ライセンス ガイドを](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)参照してください。

次のいずれかの方法を使用して、攻撃表面の縮小ルールを有効にすることができます。

- [Microsoft Intune](#intune)
- [モバイル デバイス管理 (MDM)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [グループ ポリシー](#group-policy)
- [PowerShell](#powershell)

Intuneや Microsoft エンドポイント マネージャーなどのエンタープライズ レベルの管理をお勧めします。 エンタープライズ レベルの管理では、起動時に競合するグループ ポリシーまたは PowerShell の設定が上書きされます。

## <a name="exclude-files-and-folders-from-asr-rules"></a>ASR ルールからファイルとフォルダーを除外する

ほとんどの攻撃面縮小ルールによって、ファイルとフォルダーが評価されないように除外できます。 つまり、ASR 規則によってファイルまたはフォルダーに悪意のある動作が含まれていると判断された場合でも、ファイルの実行はブロックされません。 これにより、安全でないファイルが実行され、デバイスに感染する可能性があります。

指定した Defender for Endpoint ファイルと証明書インジケーターを許可することで、ASR ルールを証明書とファイル ハッシュに基づいてトリガーから除外することもできます。 ( [インジケーターの管理に関するページを](manage-indicators.md)参照してください)。

> [!IMPORTANT]
> ファイルまたはフォルダーを除外すると、ASR 規則によって提供される保護が大幅に低下する可能性があります。 除外されたファイルの実行は許可され、レポートやイベントは記録されません。
> ASR ルールで検出すべきでないと思われるファイルが検出されている場合は、 [まず監査モードを使用してルールをテストする](attack-surface-reduction-rules-deployment-test.md#step-1-test-asr-rules-using-audit)必要があります。

個々のファイルまたはフォルダーを (フォルダー パスまたは完全修飾リソース名を使用して) 指定できますが、除外が適用されるルールを指定することはできません。 除外は、除外されたアプリケーションまたはサービスが開始されたときにのみ適用されます。 たとえば、既に実行されている更新サービスの除外を追加した場合、サービスが停止して再起動されるまで、更新サービスは引き続きイベントをトリガーします。

ASR ルールでは、環境変数とワイルドカードがサポートされます。 ワイルドカードの使用の詳細については、「 [ファイル名とフォルダーパスまたは拡張子の除外リストでワイルドカードを使用](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)する」を参照してください。

## <a name="policy-conflict"></a>ポリシーの競合

1. 競合するポリシーが MDM と GP を介して適用される場合、MDM から適用される設定が優先されます。

2. MEM マネージド デバイスの攻撃面削減ルールでは、さまざまなポリシーの設定を統合して、デバイスごとにポリシーのスーパーセットを作成する動作がサポートされるようになりました。 競合していない設定のみがマージされますが、競合している設定はルールのスーパーセットに追加されません。 以前は、2 つのポリシーに 1 つの設定の競合が含まれていた場合、両方のポリシーに競合のフラグが設定され、どちらのプロファイルの設定も展開されませんでした。 攻撃対象の縮小ルールのマージ動作は次のとおりです。
   - 次のプロファイルからの攻撃表面の縮小ルールは、ルールが適用されるデバイスごとに評価されます。
     - デバイス>構成ポリシー>エンドポイント保護プロファイル> **Microsoft Defender Exploit Guard** > [攻撃面の縮小](/mem/intune/protect/endpoint-protection-windows-10#attack-surface-reduction-rules)です。
     - エンドポイント セキュリティ> **攻撃面の縮小ポリシー** > [攻撃面の削減規則](/mem/intune/protect/endpoint-security-asr-policy#devices-managed-by-intune)。
     - エンドポイント セキュリティ> セキュリティ ベースライン> **Microsoft Defender ATP ベースライン** > [攻撃表面縮小規則](/mem/intune/protect/security-baseline-settings-defender-atp#attack-surface-reduction-rules)。
   - 競合のない設定は、デバイスのポリシーのスーパーセットに追加されます。
   - 2 つ以上のポリシーに競合する設定がある場合、競合する設定は結合されたポリシーに追加されませんが、競合しない設定は、デバイスに適用されるスーパーセット ポリシーに追加されます。
   - 競合する設定の構成のみが保持されます。

## <a name="configuration-methods"></a>構成メソッド

このセクションでは、次の構成方法の構成の詳細について説明します。

- [Intune](#intune)
- [MEM](#mem)
- [MDM](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [グループ ポリシー](#group-policy)
- [PowerShell](#powershell)

ASR ルールを有効にする手順には、ファイルとフォルダーを除外する方法について説明します。

### <a name="intune"></a>Intune

#### <a name="device-configuration-profiles"></a>デバイス構成プロファイル

1. [ **デバイス構成** \> **プロファイル] を選択します**。 既存のエンドポイント保護プロファイルを選択するか、新しいエンドポイント保護プロファイルを作成します。 新しいプロファイルを作成するには、[ **プロファイルの作成** ] を選択し、このプロファイルの情報を入力します。 [ **プロファイルの種類]** で、[ **エンドポイント保護**] を選択します。 既存のプロファイルを選択した場合は、[ **プロパティ** ] を選択し、[ **設定]** を選択します。

2. **[エンドポイント保護**] ウィンドウで[**Exploit Guard] Windows Defender** 選択し、[**攻撃面の縮小**] を選択します。 ASR 規則ごとに目的の設定を選択します。

3. [ **攻撃面の縮小] の例外** で、個々のファイルとフォルダーを入力します。 [ **インポート]** を選択して、ASR ルールから除外するファイルとフォルダーを含む CSV ファイルをインポートすることもできます。 CSV ファイル内の各行は、次のように書式設定する必要があります。

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. 3 つの構成ウィンドウで **[OK] を選択します** 。 次に、新しいエンドポイント保護ファイルを作成する場合は [ **作成** ] を選択し、既存のエンドポイント保護ファイルを編集する場合は **[保存] を** 選択します。

#### <a name="endpoint-security-policy"></a>エンドポイント セキュリティ ポリシー

1. **[Endpoint Security** Attack surface reduction]\(エンドポイント セキュリティ\>**攻撃の表面の削減**\) を選択します。 既存の ASR ルールを選択するか、新しい ASR ルールを作成します。 新しいポリシーを作成するには、[ **ポリシーの作成** ] を選択し、このプロファイルの情報を入力します。 **[プロファイルの種類**] で、[**攻撃面の縮小ルール**] を選択します。 既存のプロファイルを選択した場合は、[ **プロパティ** ] を選択し、[ **設定]** を選択します。

2. **[構成設定]** ウィンドウで[**攻撃面の削減**] を選択し、各 ASR ルールに必要な設定を選択します。

3. [ **保護する必要があるその他のフォルダーの一覧**] の **[保護されたフォルダーにアクセスできるアプリの一覧]** と [ **攻撃対象の縮小ルールからファイルとパスを除外する**] で、個々のファイルとフォルダーを入力します。 [ **インポート]** を選択して、ASR ルールから除外するファイルとフォルダーを含む CSV ファイルをインポートすることもできます。 CSV ファイル内の各行は、次のように書式設定する必要があります。

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. 3 つの構成ウィンドウで **[次へ** ] を選択し、新しいポリシーを作成する場合は [ **作成** ] を選択し、既存のポリシーを編集している場合は **[保存] を** 選択します。

### <a name="mem"></a>MEM

Microsoft エンドポイント マネージャー (MEM) OMA-URI を使用して、カスタム ASR ルールを構成できます。 次の手順では、この例のルール [「悪用された脆弱な署名されたドライバーの悪用をブロック](attack-surface-reduction-rules-reference.md#block-abuse-of-exploited-vulnerable-signed-drivers) する」を使用します。

1. Microsoft エンドポイント マネージャー (MEM) 管理センターを開きます。 **[ホーム**] メニューの [**デバイス**] をクリックし、[**構成プロファイル**] を選択して、[**プロファイルの作成**] をクリックします。

   > [!div class="mx-imgBorder"]
   >  :::image type="content" source="images/mem01-create-profile.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルの [プロファイルの作成] ページ" lightbox="images/mem01-create-profile.png":::

2. [ **プロファイルの作成**] で、次の 2 つのドロップダウン リストで、次を選択します。

   - **プラットフォーム** で **、Windows 10以降を** 選択します
   - **[プロファイルの種類]** で 、[テンプレート] を選択 **します**。
   - エンドポイント セキュリティを使用して ASR ルールが既に設定されている場合は、[**プロファイルの種類****] で [設定カタログ]** を選択します。

   [ **カスタム**] を選択し、[ **作成**] を選択します。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem02-profile-attributes.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルのルール プロファイル属性" lightbox="images/mem02-profile-attributes.png":::

3. カスタム テンプレート ツールが開き、手順 **1 の基本** に進みます。 **[1 基本]** の **[名前]** にテンプレートの名前を入力し、[**説明]** に説明を入力できます (省略可能)。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem03-1-basics.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルの基本的な属性" lightbox="images/mem03-1-basics.png":::

4. **[次へ]** をクリックします。 手順 **2 構成設定** が開きます。 OMA-URI 設定の場合は、[ **追加**] をクリックします。 [ **追加]** と [ **エクスポート**] の 2 つのオプションが表示されるようになりました。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem04-2-configuration-settings.png" alt-text="Microsoft エンドポイント マネージャー 管理センター ポータルの構成設定" lightbox="images/mem04-2-configuration-settings.png":::

5. もう一度 [ **追加]** をクリックします。 **行 OMA-URI 設定の追加が** 開きます。 [ **行の追加]** で、次の操作を行います。

   - **[名前]** にルールの名前を入力します。
   - [ **説明]** に簡単な説明を入力します。
   - **OMA-URI** で、追加するルールの特定の OMA-URI リンクを入力または貼り付けます。 この例の規則に使用する OMA-URI については、この記事の MDM セクションを参照してください。 攻撃表面の縮小ルール GUID については、「攻撃面の縮小ルール」トピックの [ルールごとの説明](attack-surface-reduction-rules-reference.md#per-rule-descriptions) を参照してください。
   - **[データ型**] で [文字列] を選択 **します**。
   - **[値]** で、GUID 値、符号、および状態値を\=スペースなしで入力または貼り付けます (_GUID=StateValue_)。 ここで、

     - 0 : 無効 (ASR 規則を無効にする)
     - 1 : ブロック (ASR 規則を有効にする)
     - 2 : 監査 (有効にした場合、ASR ルールが組織にどのような影響を与えるかを評価する)
     - 6 : 警告 (ASR ルールを有効にするが、エンド ユーザーがブロックをバイパスできるようにする)

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem05-add-row-oma-uri.png" alt-text="Microsoft エンドポイント マネージャー 管理センター ポータルの OMA URI 構成" lightbox="images/mem05-add-row-oma-uri.png":::

6. **[保存]** を選択します。 **行の追加** を閉じます。 **[カスタム]** で、[**次へ**] を選択します。 手順 **3 のスコープ タグ** では、スコープ タグは省略可能です。 次のいずれかの操作を行います。

   - [ **スコープ タグの選択]** を選択し、スコープ タグ (省略可能) を選択して、[ **次へ**] を選択します。
   - または、[**次へ**] を選択します。

7. 手順 **4[ 割り当て]** の [ **含まれるグループ**] で、このルールを適用するグループについて、次のオプションから選択します。

   - **グループの追加**
   - **すべてのユーザーを追加する**
   - **すべてのデバイスを追加する**

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem06-4-assignments.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルでの割り当て" lightbox="images/mem06-4-assignments.png":::

8. **[除外されたグループ]** で、このルールから除外するグループを選択し、[**次へ**] を選択します。

9. 次の設定の手順 **5[適用規則]** で、次の操作を行います。

   - **[ルール]** で[**プロファイルを割り当てる場合]**、または [プロファイル **を割り当てない場合はプロファイルを割り当てない**] を選択します。
   - **[プロパティ] で**、このルールを適用するプロパティを選択します。
   - **[値]** に、該当する値または値の範囲を入力します。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem07-5-applicability-rules.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルの適用規則" lightbox="images/mem07-5-applicability-rules.png":::

10. **[次へ]** を選択します。 手順 **6[確認と作成**] で、選択して入力した設定と情報を確認し、[ **作成**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mem08-6-review-create.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルの [確認と作成] オプション" lightbox="images/mem08-6-review-create.png":::

    > [!NOTE]
    > ルールはアクティブであり、数分以内に稼働します。

> [!NOTE]
> 競合処理:
>
> デバイスに 2 つの異なる ASR ポリシーを割り当てる場合、競合の処理方法は、異なる状態が割り当てられたルールであり、競合管理は行われず、結果はエラーになります。
>
> 競合しないルールではエラーが発生せず、ルールは正しく適用されます。 その結果、最初のルールが適用され、後続の競合しないルールがポリシーにマージされます。

### <a name="mdm"></a>MDM

[./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) 構成サービス プロバイダー (CSP) を使用して、各ルールのモードを個別に有効および設定します。

参照用のサンプルを次に示します。これは、 [攻撃面の縮小規則の参照](attack-surface-reduction-rules-reference.md)に GUID 値を使用しています。

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84=2|3b576869-a4ec-4529-8536-b80a7769e899=1|d4f940ab-401b-4efc-aadc-ad5f3c50688a=2|d3e037e1-3eb8-44c8-a917-57927947596d=1|5beb7efe-fd9a-4556-801d-275e5ffc04cc=0|be9ba2d9-53ea-4cdc-84e5-9b1eeee46550=1`

監査モードで有効 (ブロック)、無効化、警告、または有効にする値は次のとおりです。

- 0 : 無効 (ASR 規則を無効にする)
- 1 : ブロック (ASR 規則を有効にする)
- 2 : 監査 (有効にした場合、ASR ルールが組織にどのような影響を与えるかを評価する)
- 6 : 警告 (ASR ルールを有効にしますが、エンド ユーザーがブロックをバイパスできるようにします)。 警告モードは、ほとんどの ASR ルールで使用できます。

除外を追加するには、 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 構成サービス プロバイダー (CSP) を使用します。

例:

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> 必ずスペースを使用せずに OMA-URI 値を入力してください。

### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Microsoft Endpoint Configuration Managerで、[**資産とコンプライアンス**] \> [**エンドポイントの保護**] \> [**Windows Defender Exploit Guard**] に移動します。

2. [**ホーム**] \> [**Exploit Guard ポリシーの作成**] を選択します。

3. 名前と説明を入力し、[ **攻撃面の縮小**] を選択して、[ **次へ**] を選択します。

4. アクションをブロックまたは監査するルールを選択し、[ **次へ**] を選択します。

5. 設定を確認し、[ **次へ** ] を選択してポリシーを作成します。

6. ポリシー作成後、[**閉じる**] を選択します。

### <a name="group-policy"></a>グループ ポリシー

> [!WARNING]
> Intune、Configuration Manager、その他のエンタープライズ レベルの管理プラットフォームを使用してコンピューターやデバイスを管理する場合、管理ソフトウェアは起動時に競合するグループ ポリシー設定を上書きします。

1. グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](https://technet.microsoft.com/library/cc731212.aspx) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. **[グループ ポリシー管理エディター]** で、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。

3. ツリーを **Windows コンポーネント** \> **に展開します。Microsoft Defender ウイルス対策** \> **Microsoft Defender Exploit Guard** \> **攻撃の表面の縮小**。

4. [ **攻撃対象の縮小ルールの構成** ] を選択し、[ **有効]** を選択します。 その後、[オプション] セクションで、各ルールの個々の状態を設定できます。 **[表示]...** を選択し、[**値名**] 列にルール ID を入力し、選択した状態を [**値]** 列に次のように入力します。

   - 0 : 無効 (ASR 規則を無効にする)
   - 1 : ブロック (ASR 規則を有効にする)
   - 2 : 監査 (有効にした場合、ASR ルールが組織にどのような影響を与えるかを評価する)
   - 6 : 警告 (ASR ルールを有効にするが、エンド ユーザーがブロックをバイパスできるようにする)

   :::image type="content" source="images/asr-rules-gp.png" alt-text="グループ ポリシーの ASR 規則" lightbox="images/asr-rules-gp.png":::

5. ASR ルールからファイルとフォルダーを除外するには、[ **攻撃対象の回避ルールからファイルとパスを除外** する] 設定を選択し、オプションを **[有効]** に設定します。 [ **表示]** を選択し、[ **値名** ] 列に各ファイルまたはフォルダーを入力します。 各項目の **[値**] 列に **「0**」と入力します。

   > [!WARNING]
   > **[値名]** 列または [**値**] 列ではサポートされていないため、引用符は使用しないでください。

### <a name="powershell"></a>PowerShell

> [!WARNING]
> Intune、Configuration Manager、または別のエンタープライズ レベルの管理プラットフォームを使用してコンピューターとデバイスを管理する場合、管理ソフトウェアは起動時に競合するすべての PowerShell 設定を上書きします。 ユーザーが PowerShell を使用して値を定義できるようにするには、管理プラットフォームでルールの [ユーザー定義] オプションを使用します。
> "ユーザー定義" を使用すると、ローカル管理者ユーザーはルールを構成できます。
> ユーザー定義オプションの設定を次の図に示します。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-user-defined.png" alt-text="資格情報のセキュリティを有効にするオプション" lightbox="images/asr-user-defined.png":::

1. スタート メニューに「**powershell**」と入力し、**[Windows PowerShell]** を右クリックして **[管理者として実行]** を選択します。

2. 次のいずれかのコマンドレットを入力します。 (ルール ID など、詳細については、 [攻撃面の縮小ルールのリファレンスを参照](attack-surface-reduction-rules-reference.md) してください)。

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    監査モードで ASR ルールを有効にするには、次のコマンドレットを使用します。

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    警告モードで ASR ルールを有効にするには、次のコマンドレットを使用します。

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    悪用された脆弱な署名されたドライバーの ASR ブロックの悪用を有効にするには、次のコマンドレットを使用します。

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
   ```

    ASR 規則を無効にするには、次のコマンドレットを使用します。

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > ルールごとに個別に状態を指定する必要がありますが、コンマ区切りのリストでルールと状態を組み合わせることができます。
    >
    > 次の例では、最初の 2 つのルールが有効になり、3 番目のルールが無効になり、4 番目のルールが監査モードで有効になります。
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    PowerShell 動詞を `Add-MpPreference` 使用して、既存のリストに新しいルールを追加することもできます。

    > [!WARNING]
    > `Set-MpPreference` は常に既存のルール セットを上書きします。 既存のセットに追加する場合は、代わりに使用 `Add-MpPreference` します。
    > ルールの一覧とその現在の状態を取得するには、次を使用します `Get-MpPreference`。

3. ASR 規則からファイルとフォルダーを除外するには、次のコマンドレットを使用します。

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    引き続き使用 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` して、ファイルとフォルダーをリストに追加します。

    > [!IMPORTANT]
    > リストにアプリを追加または追加するために使用 `Add-MpPreference` します。 コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。

## <a name="related-articles"></a>関連記事

- [攻撃面の縮小ルールリファレンス](attack-surface-reduction-rules-reference.md)
- [攻撃面の縮小を評価する](evaluate-attack-surface-reduction.md)
- [攻撃面の減少の FAQ](attack-surface-reduction.md)
