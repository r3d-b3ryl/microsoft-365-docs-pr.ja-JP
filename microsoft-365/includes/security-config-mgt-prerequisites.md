---
title: ファイルを含める
description: ファイルを含める
author: mjcaparas
ms.service: microsoft-365-enterprise
ms.author: macapara
ms.openlocfilehash: 2d48c4066cc1cde102fc395d7c532d26ea2a4db0
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331541"
---
## <a name="prerequisites"></a>前提条件

Microsoft Defender for Endpoint シナリオのセキュリティ管理の要件については、次のセクションを参照してください。

### <a name="environment"></a>環境

デバイスが Microsoft Defender for Endpoint にオンボードする場合:


- デバイスは、Intune へのモバイル エンドポイント マネージャー (MDM) 登録である既存のデバイス プレゼンスについて調査されます。
- プレゼンスがエンドポイント マネージャーデバイスでは、セキュリティ管理機能が有効になります
- 信頼は、まだ存在しないAzure Active Directoryを使用して作成されます。
- Azure Active Directory信頼は、Intune (Intune) と通信しエンドポイント マネージャーポリシーを取得するために使用されます。
- ポリシーの取得エンドポイント マネージャー Microsoft Defender for Endpoint によってデバイスに適用されます。

### <a name="active-directory-requirements"></a>Active Directory の要件

ドメインに参加しているデバイスがユーザーとの信頼をAzure Active Directory、このシナリオはハイブリッド ネットワーク参加シナリオAzure Active Directory *されます*。 Microsoft Defender for Endpoint のセキュリティ管理は、次の要件を満たすこのシナリオを完全にサポートします。

- Azure Active Directory Connect (AAD Connect) は、Microsoft Defender for Endpoint から使用されるテナントに同期する必要があります。
- ハイブリッド Azure Active Directory Join は、環境で構成する必要があります (フェデレーションまたは同期AAD Connect)
- AAD Connect同期には、デバイス オブジェクトをスコープ内に含め、Azure Active Directory (参加に必要な場合)
- AAD Connect 2012 R2 の同期ルールを変更する必要があります (Server 2012 R2 のサポートが必要な場合)
- すべてのデバイスは、Microsoft Defender for Endpoint をAzure Active Directoryテナントのサーバーに登録する必要があります。 テナント間のシナリオはサポートされていません。 

### <a name="connectivity-requirements"></a>接続要件

デバイスは、次のエンドポイントにアクセスできる必要があります。

- `enterpriseregistration.windows.net`- 登録Azure AD。
- `login.microsoftonline.com`- 登録Azure AD。
- `*.dm.microsoft.com` - ワイルドカードを使用すると、登録、チェックイン、およびレポートに使用されるクラウド サービス エンドポイントがサポートされ、サービスの規模が拡大するに応じ変更される可能性があります。

### <a name="supported-platforms"></a>サポートされるプラットフォーム

Microsoft Defender for Endpoint セキュリティ管理のポリシーは、次のデバイス プラットフォームでサポートされています。

- Windows 10 Pro/Enterprise ([KB5006738)](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)
- Windows 11 Pro/Enterprise
- Windows Server 2012デバイス用 [Microsoft Defender を使用した R2 Down-Level](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- Windows Server 2016[デバイス用 Microsoft Defender Down-Levelする](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- Windows Server 2019 ([KB5006744 付](https://support.microsoft.com/topic/october-19-2021-kb5006744-os-build-17763-2268-preview-e043a8a3-901b-4190-bb6b-f5a4137411c0)き)
- Windows Server 2022 ([KB5006745 付](https://support.microsoft.com/topic/october-26-2021-kb5006745-os-build-20348-320-preview-8ff9319a-19e7-40c7-bbd1-cd70fcca066c)き)

### <a name="licensing-and-subscriptions"></a>ライセンスとサブスクリプション

Microsoft Defender for Endpoint のセキュリティ管理を使用するには、次の情報が必要です。

- Microsoft Defender for Endpoint のライセンスを付与するサブスクリプション (Microsoft 365 など)、または Microsoft Defender for Endpoint 専用のスタンドアロン ライセンス。 Microsoft Defender for Endpoint ライセンスを付与するサブスクリプションは、テナントに管理センターのエンドポイント セキュリティ ノードへのアクセス権Microsoft エンドポイント マネージャー付与します。

  > [!NOTE]  
  > **例外**: Microsoft Defender for Cloud 専用ライセンス (以前は Azure Security Center) の一部として Microsoft Defender for Endpoint にアクセスできる場合、Microsoft Defender for Endpoint 機能のセキュリティ管理は使用できません。

エンドポイント セキュリティ ノードでは、デバイスの Microsoft Defender for Endpoint を管理し、デバイスの状態を監視するためのポリシーを構成および展開します。

オプションの現在の情報については、「 [エンドポイント用 Microsoft Defender の最小要件」を参照してください](/microsoft-365/security/defender-endpoint/minimum-requirements?view=o365-worldwide&preserve-view=true)。



## <a name="architecture"></a>アーキテクチャ

次の図は、Microsoft Defender for Endpoint セキュリティ構成管理ソリューションの概念的な表現です。

:::image type="content" alt-text="Microsoft Defender for Endpoint セキュリティ構成管理ソリューションの概念的表現" source="../security/defender-endpoint/images/mde-architecture.png":::

1. Microsoft Defender for Endpoint にオンボードされているデバイス。

2. 各デバイスとデバイス間で信頼が確立Azure AD。 デバイスに既存の信頼がある場合、その信頼が使用されます。 デバイスが登録されていない場合は、新しい信頼が作成されます。

3. デバイスは、デバイスAzure AD ID を使用して、ユーザーと通信エンドポイント マネージャー。 この ID を使用Microsoft エンドポイント マネージャーデバイスを対象とするポリシーを、チェックイン時に配布できます。

4. Defender for Endpoint はポリシーの状態をレポートし、ポリシーの状態を エンドポイント マネージャー。

## <a name="which-solution-should-i-use"></a>どのソリューションを使用する必要がありますか?

Microsoft エンドポイント マネージャーには、デバイス上の Defender for Endpoint の構成を管理するためのいくつかの方法とポリシーの種類が含まれています。

デバイス保護が Defender for Endpoint の管理以外にも必要な場合は[](/mem/intune/protect/device-protect)、「デバイス保護の概要」を参照して、デバイスコンプライアンス、管理対象アプリ、アプリ保護ポリシー、サードパーティのコンプライアンスおよびモバイル脅威防御パートナーとの統合など、デバイスの保護に役立つ Microsoft エンドポイント マネージャー によって提供されるその他の機能について説明します。 

次の表は、さまざまなシナリオで管理されるデバイスでサポートされる MDE 設定を構成できるポリシーを理解するのに役立ちます。 MDE セキュリティ構成と *Microsoft エンドポイント マネージャー* の両方でサポートされているポリシーを展開する場合、そのポリシーの 1 つのインスタンスは、*MDE* のみを実行するデバイスと Intune または Configuration Manager によって管理されるデバイスによって処理できます。

| Microsoft エンドポイント マネージャー  | ワークロード | MDE セキュリティ構成  |  Microsoft エンドポイント マネージャー |
|----------------|----------------|-------------------|------------|
| エンドポイントのセキュリティ    | ウイルス対策                   | ![サポートされている](../media/green-check.png)  | ![サポートされている](../media/green-check.png)  |
|                      | ディスク暗号化   |           | ![サポート](../media/green-check.png)  |
|                      | ファイアウォール (プロファイルとルール)                | ![サポートされている](../media/green-check.png) | ![サポートされている](../media/green-check.png)  |
|                      | エンドポイントの検出および応答        | ![サポートされている](../media/green-check.png) | ![サポートされている](../media/green-check.png)  |
|                      | 攻撃面の縮小    |           | ![サポート](../media/green-check.png)  |
|                      | アカウント保護       |       | ![サポートされている](../media/green-check.png)  |
|                      | デバイスコンプライアンス     |   | ![サポートされている](../media/green-check.png)  |
|                      | 条件付きアクセス    |   | ![サポート](../media/green-check.png)  |
|                      | セキュリティ基本計画      |   | ![サポートされている](../media/green-check.png)  |

**エンドポイント セキュリティ ポリシーは、** 組織内のデバイスの保護に重点を置くセキュリティ管理者が使用することを目的とした個別の設定グループです。

- **ウイルス** 対策ポリシーは、Microsoft Defender for Endpoint にあるセキュリティ構成を管理します。 「エンドポイント  [セキュリティの](/mem/intune/protect/endpoint-security-antivirus-policy) ウイルス対策ポリシー」を参照してください。
- **攻撃表面の縮小** ポリシーは、組織がサイバー脅威や攻撃に対して脆弱な場所を最小限に抑えることに重点を置きます。 詳細については、「脅威の[保護」の](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)ドキュメントの「攻撃表面の縮小の概要Windowsエンドポイント セキュリティの攻撃[表面](/mem/intune/protect/endpoint-security-asr-policy)の縮小ポリシー」を参照してください。
- **エンドポイント検出と応答** (EDR) ポリシーは、リアルタイムでアクション可能な高度な攻撃検出を提供する Defender for Endpoint 機能を管理します。 セキュリティ アナリストは、EDR構成に基づいて、アラートを効果的に優先順位付けし、侵害の全範囲を可視化し、脅威を修復するための対応アクションを実行できます。 エンドポイント セキュリティ [については、「エンドポイントの検出と応答](/mem/intune/protect/endpoint-security-edr-policy) ポリシー」を参照してください。
- **ファイアウォール** ポリシーは、デバイス上の Defender ファイアウォールに重点を置く。 エンドポイント セキュリティ [については、「](/mem/intune/protect/endpoint-security-firewall-policy) ファイアウォール ポリシー」を参照してください。
- **ファイアウォール ルールは** 、特定のポート、プロトコル、アプリケーション、およびネットワークを含むファイアウォールの詳細なルールを構成します。 エンドポイント セキュリティ [については、「](/mem/intune/protect/endpoint-security-firewall-policy) ファイアウォール ポリシー」を参照してください。
- **セキュリティ ベースラインには、** Defender、Edge、またはセキュリティ サポートなど、さまざまな製品に対して Microsoft が推奨するセキュリティの状態を定義する事前構成済みのセキュリティ設定Windows。 既定の推奨事項は、関連する製品チームからの推奨事項であり、推奨される安全な構成をデバイスに迅速に展開できます。 各ベースラインで設定が事前構成されている間、カスタマイズされたインスタンスを作成して組織のセキュリティの期待を確立できます。 「Intune [のセキュリティ ベースライン](/mem/intune/protect/security-baselines) 」を参照してください。

## <a name="configure-your-tenant-to-support-microsoft-defender-for-endpoint-security-configuration-management"></a>Microsoft Defender for Endpoint Security Configuration Management をサポートするためにテナントを構成する

Microsoft Defender for Endpoint のセキュリティ構成管理を Microsoft エンドポイント マネージャー管理センターでサポートするには、各コンソールから Microsoft Defender 間の通信を有効にする必要があります。

1. ポータルに [サインインMicrosoft 365 Defender、](https://security.microsoft.com/)**設定** > **EndpointsConfiguration** >  **ManagementEnforcement** >  Scope に移動し、セキュリティ設定管理のプラットフォームを有効にします。

   :::image type="content" source="../media/enable-mde-settings-management-defender.png" alt-text="Defender コンソールで Microsoft Defender for Endpoint の設定管理を有効にします。":::

2. 関連するユーザーが、Defender ポータルで役割を構成して、Microsoft エンドポイント マネージャーエンドポイント セキュリティ設定を管理するアクセス許可を持っているか、またはそれらのアクセス許可を付与します。 [**RolesAdd****] 設定** > に > **移動します**。

   :::image type="content" source="../media/add-role-in-mde.png" alt-text="Defender ポータルで新しい役割を作成します。":::

   > [!TIP]
   > 既存の役割を変更し、必要なアクセス許可を追加したり、Microsoft Defender for Endpoint で追加の役割を作成したりすることはできません。

3. 役割を構成する場合は、ユーザーを追加し、次の手順で [エンドポイント セキュリティ設定の管理] を **選択Microsoft エンドポイント マネージャー**。

   :::image type="content" source="../media/add-role.png" alt-text="設定を管理するためのアクセス許可をユーザーに付与します。":::

4. Microsoft エンドポイント マネージャー管理センター

5. [ **エンドポイント セキュリティ** > **Microsoft Defender for Endpoint**] を選択し、[エンドポイントの Microsoft Defender for Endpoint を許可する] を [エンドポイント セキュリティ構成 **(プレビュー) を適用する] を [オン]** に **設定します**。

   :::image type="content" source="../media/enable-mde-settings-management-mem.png" alt-text="管理センターで Microsoft Defender for Endpoint の設定管理Microsoft エンドポイント マネージャー有効にします。":::

   このオプションを *[オン*] に設定すると、Microsoft エンドポイント マネージャー によって管理されていない Microsoft Defender for Endpoint のプラットフォーム スコープ内のすべてのデバイスが、Microsoft Defender for Endpoint にオンボードされる資格があります。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>デバイスを Microsoft Defender for Endpoint にオンボードする

Microsoft Defender for Endpoint では、オンボード デバイスに対して複数のオプションがサポートされています。 現在のガイダンスについては、「[Defender](/microsoft-365/security/defender-endpoint/security-config-management) for Endpoint」のドキュメントの「Windowsデバイスのオンボーディング ツールとメソッド」を参照してください。


> [!IMPORTANT]
> デバイスが Microsoft Defender for Endpoint にオンボードされた後、Microsoft Defender for Endpoint のセキュリティ管理に登録する前に、 **MDE-Management** にタグ付けする必要があります。 MDE でのデバイス タグ付けの詳細については、「デバイス タグの作成と [*管理」を参照してください*](/microsoft-365/security/defender-endpoint/machine-tags)。


## <a name="co-existence-with-microsoft-endpoint-configuration-manager"></a>ユーザーとのMicrosoft Endpoint Configuration Manager
Configuration Manager を使用する場合、セキュリティ ポリシーの管理に最適なパスは、 [Configuration Manager テナント接続を使用する方法です](/mem/configmgr/tenant-attach/endpoint-security-get-started)。 環境によっては、Microsoft Defender のセキュリティ管理を使用することが望ましい場合があります。 Configuration Manager で Microsoft Defender のセキュリティ管理を使用する場合は、エンドポイント セキュリティ ポリシーを 1 つのコントロール プレーンに分離する必要があります。 両方のチャネルを通じてポリシーを制御すると、競合や望ましくない結果が生じることができます。


## <a name="create-azure-ad-groups"></a>グループAzure AD作成

Defender for Endpoint にデバイスをオンボードした後、Microsoft Defender for Endpoint のポリシーの展開をサポートするデバイス グループを作成する必要があります。

Microsoft Defender for Endpoint に登録されているが、Intune または Configuration Manager によって管理されていないデバイスを識別するには、次の方法を実行します。

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にサインインします。

2. [**DevicesAll デバイス]** >  に移動し、[管理] 列を **選択** してデバイスのビューを並べ替えます。

   Microsoft Defender for Endpoint にオンボードされ、登録されているが Intune によって管理されていないデバイスでは、[管理] 列に **Microsoft Defender for Endpoint** *が表示* されます。 これらは、Microsoft Defender for Endpoint のセキュリティ管理のポリシーを受け取るデバイスです。

   Microsoft Defender for Endpoint のセキュリティ管理を使用しているデバイスの 2 つのラベルも表示されます。

   - **MDEJoined** - このシナリオの一部としてディレクトリに参加しているデバイスに追加されました。
   - **MDEManaged** - セキュリティ管理シナリオをアクティブに使用しているデバイスに追加されました。 Defender for Endpoint がセキュリティ構成の管理を停止した場合、このタグはデバイスから削除されます。

これらのデバイスのグループは、[Azure AD管理](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)[センター内Microsoft エンドポイント マネージャーできます](/mem/intune/fundamentals/groups-add)。

## <a name="deploy-policy"></a>ポリシーを展開する

Microsoft Defender for Endpoint が管理するデバイスを含む 1 つ以上の Azure AD グループを作成した後、Microsoft Defender for Endpoint のセキュリティ管理に関する次のポリシーを作成し、それらのグループに展開できます。

- ウイルス対策
- ファイアウォール
- ファイアウォールルール
- エンドポイントの検出と応答

> [!TIP]
> 同じ設定を管理する複数のポリシーをデバイスに展開しないようにします。
>
> Microsoft エンドポイント マネージャーは、各エンドポイント セキュリティ ポリシーの種類の複数のインスタンスを同じデバイスに展開し、各ポリシー インスタンスはデバイスによって個別に受信されます。 したがって、デバイスは異なるポリシーから同じ設定に対して個別の構成を受け取り、競合が発生する可能性があります。 一部の設定 (ウイルス対策の除外など) はクライアントで結合され、正常に適用されます。

1. Microsoft エンドポイント マネージャー管理センター

2. [エンドポイント セキュリティ **] に移動** し、構成するポリシーの種類 (ウイルス対策またはファイアウォール) を選択し、[ポリシーの作成] **を選択します**。

3. 次のプロパティまたは選択したポリシーの種類を入力します。

   - ウイルス対策ポリシーの場合は、次の項目を選択します。
     - プラットフォーム: **Windows 10、Windows 11、および Windows サーバー (プレビュー)**
     - プロファイル: **Microsoft Defender ウイルス対策 (プレビュー)**

   - ファイアウォール ポリシーの場合は、次の項目を選択します。
     - プラットフォーム: **Windows 10、Windows 11、および Windows サーバー (プレビュー)**
     - プロファイル: **Microsoft Defender ファイアウォール (プレビュー)**

   - [ファイアウォール ルール] ポリシーで、次の項目を選択します。
     - プラットフォーム: **Windows 10、Windows 11、および Windows サーバー (プレビュー)**
     - プロファイル: **Microsoft Defender ファイアウォール ルール (プレビュー)**

   - [エンドポイントの検出と応答] ポリシーで、次の項目を選択します。
     - プラットフォーム: **Windows 10、Windows 11、および Windows サーバー (プレビュー)**
     - プロファイル: **エンドポイントの検出と応答 (プレビュー)**

   >[!Note]
   > これらのプロファイルは、モバイル デバイス管理 (MDM) と Microsoft Intune を介して通信するデバイスと、Microsoft Defender for Endpoint クライアントを使用して通信しているデバイスの両方に適用されます。
   >
   > 必要に応じて、ターゲット設定とグループを確認してください。

4. **[作成]** を選択します。

5. **[基本]** ページでプロファイルに名前と説明を入力し、**[次へ]** を選択します。

6. [構成 **設定] ページ** で、このプロファイルで管理する設定を選択します。 設定の詳細については、その情報ダイアログを展開し、[詳細]  リンクを選択して、オンライン ドキュメントの設定の CSP 情報を表示します。

   設定の構成が完了したら、**[次へ]** を選択します。

7. [割 **り当て]** ページで、このプロファイルをAzure ADグループを選択します。 プロファイルの割り当ての詳細については、[ユーザーおよびデバイス プロファイルの割り当て](/mem/intune/configuration/device-profile-assign)に関するページを参照してください。

   [**次へ**] を選んで続行します。

   > [!TIP]
   >
   > - 割り当てフィルターは、セキュリティ構成管理プロファイルではサポートされていません。
   > - Microsoft Defender *for Endpoint* 管理には、デバイス オブジェクトだけが適用されます。 ユーザーのターゲット設定はサポートされていません。
   > - 構成されたポリシーは、エンドポイント クライアントMicrosoft Intune Microsoft Defender の両方に適用されます。

8. ポリシーの作成プロセスを完了し、[確認と作成] **ページで** [作成] を選択 **します**。 作成したプロファイルのポリシーの種類を選択すると、新しいプロファイルが一覧に表示されます。

9. ポリシーが割り当てられるのを待ち、ポリシーが適用されたという成功の兆候を表示します。

10. [Get-MpPreference](/powershell/module/defender/get-mppreference#examples) コマンド ユーティリティを使用して、設定がクライアントにローカルに適用されたと検証できます。
