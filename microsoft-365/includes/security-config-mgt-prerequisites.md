---
title: ファイルを含める
description: ファイルを含める
author: mjcaparas
ms.service: microsoft-365-security
ms.author: macapara
ms.openlocfilehash: 6fc45df2c8b63292e43674f1e8392c9407f92bd5
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67484045"
---
## <a name="prerequisites"></a>前提条件

Microsoft Defender for Endpoint シナリオのセキュリティ管理の要件については、次のセクションを参照してください。

### <a name="environment"></a>環境

デバイスがMicrosoft Defender for Endpointにオンボードされた場合:


- デバイスは、Intuneへのモバイル デバイス管理 (MDM) 登録である既存のエンドポイント マネージャープレゼンスについて調査されます。
- エンドポイント マネージャーが存在しないデバイスでは、Security Management 機能が有効になります
- Azure Active Directory が存在しない場合は、信頼が作成されます
- Azure Active Directory 信頼は、エンドポイント マネージャー (Intune) と通信し、ポリシーを取得するために使用されます
- エンドポイント マネージャーから取得したポリシーは、Microsoft Defender for Endpointによってデバイスに適用されます

### <a name="active-directory-requirements"></a>Active Directory の要件

ドメインに参加しているデバイスが Azure Active Directory との信頼関係を作成する場合、このシナリオは *ハイブリッド Azure Active Directory Join* シナリオと呼ばれます。 Microsoft Defender for Endpointの Security Management は、次の要件を満たすこのシナリオを完全にサポートしています。

- Azure Active Directory Connect (AAD Connect) は、Microsoft Defender for Endpointから使用されるテナントに同期する必要があります。
- ハイブリッド Azure Active Directory Join は、環境内で構成する必要があります (フェデレーションまたは AAD Connect Sync を使用)
- AAD Connect Sync には、Azure Active Directory と同期するために *スコープ内の* デバイス オブジェクトを含める必要があります (参加に必要な場合)
- [サーバー 2012 R2 の同期に関する](/microsoft-365/security/defender-endpoint/troubleshoot-security-config-mgt#instructions-for-applying-computer-join-rule-in-aad-connect) AAD Connect 規則を変更する必要があります (Server 2012 R2 のサポートが必要な場合)
- すべてのデバイスは、Microsoft Defender for Endpointをホストするテナントの Azure Active Directory に登録する必要があります。 テナント間のシナリオはサポートされていません。 

### <a name="connectivity-requirements"></a>接続要件

デバイスは、次のエンドポイントにアクセスできる必要があります。

- `enterpriseregistration.windows.net` - Azure AD 登録の場合。
- `login.microsoftonline.com` - Azure AD 登録の場合。
- `*.dm.microsoft.com` - ワイルドカードを使用すると、登録、チェックイン、レポートに使用されるクラウド サービス エンドポイントがサポートされ、サービスのスケーリングに応じて変更される可能性があります。

> [!Note]
> 組織のユーザーが Secure Socket Layer (SSL) 検査を行う場合は、エンドポイントを検査から除外する必要があります。

### <a name="supported-platforms"></a>サポートされるプラットフォーム

Microsoft Defender for Endpointセキュリティ管理のポリシーは、次のデバイス プラットフォームでサポートされています。

- Windows 10 Professional/Enterprise ([KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) を使用)
- Windows 11 Professional/Enterprise
- [Microsoft Defender for Down-Level デバイスを使用した R2 のWindows Server 2012](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- [Microsoft Defender for Down-Level デバイスのWindows Server 2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- Windows Server 2019 ( [KB5006744](https://support.microsoft.com/topic/october-19-2021-kb5006744-os-build-17763-2268-preview-e043a8a3-901b-4190-bb6b-f5a4137411c0) を使用)
- Windows Server 2022 ( [KB5006745](https://support.microsoft.com/topic/october-26-2021-kb5006745-os-build-20348-320-preview-8ff9319a-19e7-40c7-bbd1-cd70fcca066c) を使用)

### <a name="licensing-and-subscriptions"></a>ライセンスとサブスクリプション

Microsoft Defender for Endpointにセキュリティ管理を使用するには、次のものが必要です。

- Microsoft 365 などのMicrosoft Defender for Endpointのライセンスを付与するサブスクリプション、またはMicrosoft Defender for Endpointのみのスタンドアロン ライセンス。 Microsoft Defender for Endpoint ライセンスを付与するサブスクリプションでは、Microsoft エンドポイント マネージャー管理センターのエンドポイント セキュリティ ノードへのテナント アクセスも許可されます。

  > [!NOTE]  
  > **例外**: Microsoft Defender for Cloud 専用ライセンス (以前はAzure Security Center) の一部としてMicrosoft Defender for Endpointにアクセスできる場合、Microsoft Defender for Endpointのセキュリティ管理機能は使用できません。

エンドポイント セキュリティ ノードでは、デバイスのMicrosoft Defender for Endpointを管理し、デバイスの状態を監視するポリシーを構成して展開します。

オプションの現在の情報については、「[Microsoft Defender for Endpointの最小要件」を](/microsoft-365/security/defender-endpoint/minimum-requirements?view=o365-worldwide&preserve-view=true)参照してください。



## <a name="architecture"></a>アーキテクチャ

次の図は、Microsoft Defender for Endpointセキュリティ構成管理ソリューションの概念的な表現です。

:::image type="content" alt-text="Microsoft Defender for Endpointセキュリティ構成管理ソリューションの概念的表現" source="../security/defender-endpoint/images/mde-architecture.png":::

1. Microsoft Defender for Endpointにオンボードされるデバイス。

2. 各デバイスと Azure AD の間に信頼が確立されます。 デバイスに既存の信頼がある場合は、それが使用されます。 デバイスが登録されていない場合は、新しい信頼が作成されます。

3. デバイスは、Azure AD ID を使用してエンドポイント マネージャーと通信します。 この ID を使用すると、Microsoft エンドポイント マネージャーは、チェックイン時にデバイスを対象とするポリシーを配布できます。

4. Defender for Endpoint は、ポリシーの状態をエンドポイント マネージャーに報告します。

## <a name="which-solution-should-i-use"></a>どのソリューションを使用する必要がありますか?

Microsoft エンドポイント マネージャーには、デバイス上の Defender for Endpoint の構成を管理するためのいくつかの方法とポリシーの種類が含まれています。

デバイス保護が Defender for Endpoint の管理以外にも必要な場合は、「[デバイス保護の概要](/mem/intune/protect/device-protect)」を参照して、デバイス *のコンプライアンス*、*マネージド アプリ*、*アプリ保護ポリシー*、サード パーティのコンプライアンスおよび *モバイル脅威防御* パートナーとの統合など、デバイスの保護に役立つ Microsoft エンドポイント マネージャーによって提供される追加機能について説明します。

次の表は、さまざまなシナリオで管理されているデバイスで MDE 設定を構成できるポリシーを理解するのに役立ちます。 *MDE セキュリティ構成* と *Microsoft エンドポイント マネージャー* の両方でサポートされているポリシーを展開する場合、そのポリシーの 1 つのインスタンスは、Microsoft Defender for Endpointのみを実行するデバイスと、Intuneまたは Microsoft Intuneによって管理されるデバイスによって処理できます。Configuration Manager。

| Microsoft エンドポイント マネージャー  | Workload |ポリシー| MDE セキュリティ構成  |  Microsoft エンドポイント マネージャー |
|----------------|----------------|-------------------|------------|
| エンドポイントのセキュリティ    | ウイルス対策   |     ウイルス対策           | ![サポート](../media/green-check.png)  | ![サポート](../media/green-check.png)  |
|                      | ウイルス対策   |   ウイルス対策の除外   | ![サポート](../media/green-check.png)  | ![サポートされている](../media/green-check.png)  |
|                      | ウイルス対策   | Windows セキュリティ エクスペリエンス |                        | ![サポート](../media/green-check.png)  |
|                      | ディスク暗号化   |     すべて |      | ![サポート](../media/green-check.png)  |
|                      | ファイアウォール   | ファイアウォール              | ![サポート](../media/green-check.png) | ![サポート](../media/green-check.png)  |
|                      | ファイアウォール | ファイアウォール規則                | ![サポート](../media/green-check.png) | ![サポート](../media/green-check.png)  |
|                      | エンドポイントの検出および応答   | エンドポイントの検出および応答 | ![サポート](../media/green-check.png) | ![サポートされている](../media/green-check.png)  |
|                      | 攻撃面の縮小    |   すべて |          | ![サポート](../media/green-check.png)  |
|                      | アカウント保護       |    すべて |     | ![サポートされている](../media/green-check.png)  |
|                      | デバイス コンプライアンス     |   すべて |  | ![サポート](../media/green-check.png)  |
|                      | 条件付きアクセス    |   すべて |  | ![サポートされている](../media/green-check.png)  |
|                      | セキュリティ基本計画      |  すべて |   | ![サポート](../media/green-check.png)  |

**エンドポイント セキュリティ ポリシー** は、組織内のデバイスの保護に重点を置くセキュリティ管理者が使用することを目的とした個別の設定グループです。

- **ウイルス対策** ポリシーは、Microsoft Defender for Endpointで見つかったセキュリティ構成を管理します。 エンドポイント のセキュリティに関する  [ウイルス対策](/mem/intune/protect/endpoint-security-antivirus-policy) ポリシーを参照してください。
- **攻撃面の削減** ポリシーは、組織がサイバー脅威や攻撃に対して脆弱な場所を最小限に抑えることに重点を置きます。 詳細については、Windows 脅威保護に関するドキュメントの [攻撃面の縮小の概要](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction) と、エンドポイント セキュリティに関する [攻撃面の縮小](/mem/intune/protect/endpoint-security-asr-policy) ポリシーに関するページを参照してください。
- **エンドポイント検出と応答** (EDR) ポリシーは、ほぼリアルタイムで実行可能な高度な攻撃検出を提供する Defender for Endpoint 機能を管理します。 EDR 構成に基づいて、セキュリティ アナリストはアラートを効果的に優先順位付けし、侵害の全範囲を把握し、脅威を修復するための対応アクションを実行できます。 エンドポイントのセキュリティに関する [エンドポイントの検出と応答](/mem/intune/protect/endpoint-security-edr-policy) ポリシーに関する説明を参照してください。
- **ファイアウォール** ポリシーは、デバイス上の Defender ファイアウォールに重点を置きます。 エンドポイント のセキュリティに関する [ファイアウォール](/mem/intune/protect/endpoint-security-firewall-policy) ポリシーを参照してください。
- **ファイアウォール規則では** 、特定のポート、プロトコル、アプリケーション、ネットワークなど、ファイアウォールの詳細な規則を構成します。 エンドポイント のセキュリティに関する [ファイアウォール](/mem/intune/protect/endpoint-security-firewall-policy) ポリシーを参照してください。
- **セキュリティ ベースラインには、** Defender、Edge、Windows などのさまざまな製品に対して Microsoft が推奨するセキュリティ体制を定義する事前構成済みのセキュリティ設定が含まれます。 既定の推奨事項は、関連する製品チームからのものであり、推奨されるセキュリティで保護された構成をデバイスに迅速に展開できます。 設定は各ベースラインで事前構成されていますが、カスタマイズされたインスタンスを作成して、組織のセキュリティに関する期待を確立できます。 Intune[のセキュリティ ベースライン](/mem/intune/protect/security-baselines)を参照してください。

## <a name="configure-your-tenant-to-support-microsoft-defender-for-endpoint-security-configuration-management"></a>Microsoft Defender for Endpointセキュリティ構成管理をサポートするようにテナントを構成する

Microsoft エンドポイント マネージャー 管理センターを通じてMicrosoft Defender for Endpointセキュリティ構成管理をサポートするには、各コンソール内からそれらの間の通信を有効にする必要があります。

1. [Microsoft 365 Defender ポータル](https://security.microsoft.com/)にサインインし **、Settings** > **Endpoints** > **Configuration Management****Enforcement Scope** に移動し、セキュリティ設定管理 > 用のプラットフォームを有効にします。

   :::image type="content" source="../media/security-settings-mgt.png" alt-text="Defender コンソールでMicrosoft Defender for Endpoint設定管理を有効にします。":::
    
1. 組織のニーズに合わせてパイロット モードとConfiguration Manager機関の設定を構成します。

   :::image type="content" source="../media/pilot-CMAuthority-mde-settings-management-defender.png" alt-text="Microsoft 365 Defender ポータルでエンドポイント設定管理のパイロット モードを構成します。":::
   
  > [!TIP]
  > パイロット モードと適切なデバイス タグを使用して、少数のデバイスでロールアウトをテストして検証します。 パイロット モードを使用しないと、構成されたスコープに該当するすべてのデバイスが自動的に登録されます。

1. 関連するユーザーが Microsoft エンドポイント マネージャーでエンドポイント セキュリティ設定を管理するアクセス許可を持っているか、Defender ポータルでロールを構成してそれらのアクセス許可を付与するアクセス許可を持っていることを確認します。 **[設定****ロール** > **の追加]** >  項目に移動します。

   :::image type="content" source="../media/add-role-in-mde.png" alt-text="Defender ポータルで新しいロールを作成します。":::

   > [!TIP]
   > 既存のロールを変更し、必要なアクセス許可を追加したり、Microsoft Defender for Endpointで追加のロールを作成したりできます。

1. ロールを構成するときは、ユーザーを追加し、**Microsoft エンドポイント マネージャーで [エンドポイント セキュリティ設定の管理**] を必ず選択します。

   :::image type="content" source="../media/add-role.png" alt-text="設定を管理するためのアクセス許可をユーザーに付与します。":::

1. Microsoft エンドポイント マネージャー管理センター

1. [**エンドポイント セキュリティ****]Microsoft Defender for Endpoint** を選択し、[**エンドポイント セキュリティ構成 (プレビュー) を適用するMicrosoft Defender for Endpointを許可する]** を **[オン]** に設定します。 > 

   :::image type="content" source="../media/enable-mde-settings-management-mem.png" alt-text="Microsoft エンドポイント マネージャー 管理センターでMicrosoft Defender for Endpoint設定管理を有効にします。":::

   このオプションを *[オン]* に設定すると、Microsoft エンドポイント マネージャーによって管理されていないMicrosoft Defender for Endpointのプラットフォーム スコープ内のすべてのデバイスは、Microsoft Defender for Endpointにオンボードする資格があります。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>デバイスを Microsoft Defender for Endpoint にオンボードする

Microsoft Defender for Endpointでは、デバイスをオンボードするためのいくつかのオプションがサポートされています。 現在のガイダンスについては、Defender for Endpoint のドキュメントの [「Windows デバイスのオンボード ツールとメソッド](/microsoft-365/security/defender-endpoint/security-config-management) 」を参照してください。



## <a name="co-existence-with-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Managerとの共存
一部の環境では、[テナントがアタッチ](/mem/configmgr/tenant-attach/endpoint-security-get-started)Configuration Manager Microsoft Defender for Endpointに Security Management を使用することが望ましい場合があります。 両方を使用する場合は、複数のチャネルを使用すると競合や望ましくない結果の機会が生じるので、1 つのチャネルでポリシーを制御する必要があります。

これをサポートするには、[セキュリティの *管理] 設定* を [オフ] に切り替Configuration Manager使用して構成 *します*。  [Microsoft 365 Defender ポータル](https://security.microsoft.com/)にサインインし、**Settings** > **Endpoints** > **Configuration Management** > **Enforcement Scope** に移動します。

:::image type="content" source="../media/manage-security-settings-cfg-mgr.png" alt-text="Configuration Manager設定を使用してセキュリティ設定を管理します。":::

>[!NOTE]
>Configuration ManagerでMicrosoft Defender for Endpointに Security Management を使用する場合は、エンドポイント セキュリティ ポリシーを 1 つのコントロール プレーンに分離する必要があります。 両方のチャネルでポリシーを制御すると、競合や望ましくない結果が発生する可能性があります。


## <a name="create-azure-ad-groups"></a>Azure AD グループを作成する

デバイスが Defender for Endpoint にオンボードされたら、Microsoft Defender for Endpointのポリシーの展開をサポートするデバイス グループを作成する必要があります。

Microsoft Defender for Endpointに登録されているが、IntuneまたはConfiguration Managerによって管理されていないデバイスを識別するには、

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にサインインします。

2. [**すべてのデバイス]** >  に移動し、[**管理対象**] 列を選択してデバイスのビューを並べ替えます。

   Microsoft Defender for Endpointにオンボードされ、登録されているが、Intuneによって管理されていないデバイスは、[*Managed by*] 列 **にMicrosoft Defender for Endpoint** を表示します。 これらは、Microsoft Defender for Endpointのセキュリティ管理のポリシーを受け取ることができるデバイスです。

   また、Microsoft Defender for Endpointにセキュリティ管理を使用しているデバイスの 2 つのラベルもあります。

   - **MDEJoined** - このシナリオの一環としてディレクトリに参加しているデバイスに追加されました。
   - **MDEManaged** - セキュリティ管理シナリオを積極的に使用しているデバイスに追加されます。 Defender for Endpoint がセキュリティ構成の管理を停止した場合、このタグはデバイスから削除されます。

これらのデバイスのグループは[、Azure AD](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) または [Microsoft エンドポイント マネージャー管理センター内から](/mem/intune/fundamentals/groups-add)作成できます。

## <a name="deploy-policy"></a>ポリシーを展開する

Microsoft Defender for Endpointによって管理されているデバイスを含む 1 つ以上の Azure AD グループを作成した後、それらのグループにMicrosoft Defender for Endpoint用の Security Management の次のポリシーを作成してデプロイできます。

- ウイルス対策
- ファイアウォール
- ファイアウォール規則
- エンドポイントの検出と対応

> [!TIP]
> 同じ設定を管理する複数のポリシーをデバイスに展開しないでください。
>
> Microsoft エンドポイント マネージャーでは、各エンドポイント セキュリティ ポリシーの種類の複数のインスタンスを同じデバイスにデプロイできます。各ポリシー インスタンスはデバイスによって個別に受信されます。 そのため、デバイスは、異なるポリシーから同じ設定に対して個別の構成を受け取り、競合が発生する可能性があります。 一部の設定 (ウイルス対策の除外など) はクライアントにマージされ、正常に適用されます。

1. Microsoft エンドポイント マネージャー管理センター

2. **[エンドポイント セキュリティ]** に移動し、構成するポリシーの種類 (ウイルス対策またはファイアウォール) を選択し、[**ポリシーの作成**] を選択します。

3. 次のプロパティまたは選択したポリシーの種類を入力します。

   - ウイルス対策ポリシーの場合は、次を選択します。
     - プラットフォーム: **Windows 10、Windows 11、Windows Server (プレビュー)**
     - プロファイル: **Microsoft Defender ウイルス対策 (プレビュー)**

   - ファイアウォール ポリシーの場合は、次を選択します。
     - プラットフォーム: **Windows 10、Windows 11、Windows Server (プレビュー)**
     - プロファイル: **Microsoft Defender ファイアウォール (プレビュー)**

   - ファイアウォール規則ポリシーの場合は、次を選択します。
     - プラットフォーム: **Windows 10、Windows 11、Windows Server (プレビュー)**
     - プロファイル: **Microsoft Defender ファイアウォール規則 (プレビュー)**

   - [エンドポイントの検出と応答] ポリシーで、次を選択します。
     - プラットフォーム: **Windows 10、Windows 11、Windows Server (プレビュー)**
     - プロファイル: **エンドポイントの検出と応答 (プレビュー)**

   >[!Note]
   > これらのプロファイルは、モバイル デバイス管理 (MDM) とMicrosoft Intuneを介して通信するデバイスと、Microsoft Defender for Endpoint クライアントを使用して通信しているデバイスの両方に適用されます。
   >
   > 必要に応じて、ターゲット設定とグループを確認してください。

4. **[作成]** を選択します。

5. **[基本]** ページでプロファイルに名前と説明を入力し、**[次へ]** を選択します。

6. [ **構成設定]** ページで、このプロファイルで管理する設定を選択します。 設定の詳細については、その情報ダイアログを展開し、[ *詳細情報* ] リンクを選択して、設定の CSP 情報をオンライン ドキュメントに表示します。

   設定の構成が完了したら、**[次へ]** を選択します。

7. [ **割り当て]** ページで、このプロファイルを受け取る Azure AD グループを選択します。 プロファイルの割り当ての詳細については、[ユーザーおよびデバイス プロファイルの割り当て](/mem/intune/configuration/device-profile-assign)に関するページを参照してください。

   [**次へ**] を選んで続行します。

   > [!TIP]
   >
   > - 割り当てフィルターは、セキュリティ構成管理プロファイルではサポートされていません。
   > - デバイス *オブジェクト* のみがMicrosoft Defender for Endpoint管理に適用されます。 ターゲット ユーザーはサポートされていません。
   > - 構成されたポリシーは、Microsoft Intune クライアントとMicrosoft Defender for Endpoint クライアントの両方に適用されます

8. ポリシー作成プロセスを完了し、[ **確認と作成** ] ページで [ **作成**] を選択します。 作成したプロファイルのポリシーの種類を選択すると、新しいプロファイルが一覧に表示されます。

9. ポリシーが割り当てられるのを待ち、ポリシーが適用されたことを示す成功を確認します。

10. [Get-MpPreference](/powershell/module/defender/get-mppreference#examples) コマンド ユーティリティを使用して、設定がクライアントにローカルに適用されていることを検証できます。
