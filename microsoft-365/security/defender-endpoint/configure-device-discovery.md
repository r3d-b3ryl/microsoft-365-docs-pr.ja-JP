---
title: デバイス検出の構成
description: 基本または標準の検出を使用してMicrosoft 365 Defenderでデバイス検出を構成する方法について説明します
keywords: basic, standard, エンドポイント検出の構成, デバイス検出
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 77dbdb290a0f8643bd24e1a3c561b823e5c2e4b3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330595"
---
# <a name="configure-device-discovery"></a>デバイス検出の構成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


検出は、標準モードまたは基本モードで構成できます。 標準オプションを使用して、ネットワーク内のデバイスを積極的に検索します。これにより、エンドポイントの検出が保証され、より豊富なデバイス分類が提供されます。

標準検出の実行に使用されるデバイスの一覧をカスタマイズできます。 この機能もサポートしているすべてのオンボード デバイスで標準検出を有効にするか (現在 - Windows 10 以降および Windows Server 2019 以降のデバイスのみ) するか、デバイス タグを指定してデバイスのサブセットまたはサブセットを選択します。

## <a name="set-up-device-discovery"></a>デバイス検出を設定する

デバイス検出を設定するには、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で次の構成手順を実行します。

**設定** > **Device 検出** に移動する

1. オンボードされたデバイスで使用する検出モードとして Basic を構成する場合は、[**基本**] を選択し、[保存] を選択 **します**。
2. Standard Discovery の使用を選択した場合は、アクティブなプローブに使用するデバイス (すべてのデバイスまたはサブセット) をデバイス タグを指定して選択し、[保存] を選択 **します**。

> [!NOTE]
>Standard Discovery では、さまざまな PowerShell スクリプトを使用して、ネットワーク内のデバイスを積極的にプローブします。 これらの PowerShell スクリプトは Microsoft によって署名され、次の場所 `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`から実行されます。 たとえば、「 `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1` 」のように入力します。

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>標準検出で積極的にプローブされるデバイスを除外する

ネットワーク上にアクティブにスキャンすべきでないデバイス (たとえば、別のセキュリティ ツールのハニーポットとして使用されるデバイス) がある場合は、除外の一覧を定義してスキャンされないようにすることもできます。 デバイスは引き続き Basic 検出モードを使用して検出でき、マルチキャスト検出の試行を通じて検出することもできます。 これらのデバイスは受動的に検出されますが、積極的にプローブされることはありません。

除外するデバイスは、[ **除外]** ページで構成できます。

## <a name="select-networks-to-monitor"></a>監視するネットワークを選択する

Microsoft Defender for Endpointはネットワークを分析し、監視する必要がある企業ネットワークか、無視できる企業以外のネットワークかを判断します。 ネットワークを企業として識別するために、すべてのテナントのクライアント間でネットワーク識別子を関連付けます。また、組織内のデバイスの大半が、同じ既定のゲートウェイと DHCP サーバー アドレスを持つ同じネットワーク名に接続されていることを報告する場合は、これが企業ネットワークであると見なします。 通常、企業ネットワークは監視対象として選択されます。 ただし、オンボードされたデバイスが見つかった企業以外のネットワークを監視することを選択することで、この決定をオーバーライドできます。

監視するネットワークを指定することで、デバイス検出を実行できる場所を構成できます。 ネットワークが監視されると、デバイス検出をそのネットワークで実行できます。

デバイス検出を実行できるネットワークの一覧が、[ **監視対象ネットワーク** ] ページに表示されます。

> [!NOTE]
> 一覧には、企業ネットワークとして識別されたネットワークが表示されます。 50 未満のネットワークが企業ネットワークとして識別されている場合、最もオンボードされたデバイスを含む最大 50 個のネットワークが一覧表示されます。

監視対象のネットワークの一覧は、過去 7 日間にネットワークに表示されたデバイスの合計数に基づいて並べ替えられます。

フィルターを適用して、次のいずれかのネットワーク検出状態を表示できます。

- **監視対象のネットワーク** - デバイス検出が実行されるネットワーク。
- **無視されたネットワーク** - このネットワークは無視され、デバイス検出は実行されません。
- **すべて** - 監視されているネットワークと無視されたネットワークの両方が表示されます。

### <a name="configure-the-network-monitor-state"></a>ネットワーク モニターの状態を構成する

デバイス検出が行われる場所を制御します。 監視対象のネットワークは、デバイス検出が実行される場所であり、通常は企業ネットワークです。 また、ネットワークを無視するか、状態を変更した後で最初の検出分類を選択することもできます。

最初の検出分類を選択すると、既定のシステムによって作成されたネットワーク モニターの状態が適用されます。 既定のシステム作成ネットワーク モニターの状態を選択すると、企業として識別されたネットワークが監視され、企業以外として識別されたネットワークは自動的に無視されます。

1. **[設定 >デバイス検出] を選択します**。
2. [ **監視対象ネットワーク**] を選択します。
3. ネットワークの一覧を表示します。
4. ネットワーク名の横にある 3 つのドットを選択します。
5. 最初の検出分類を監視するか、無視するか、または使用するかを選択します。

    > [!WARNING]
    >
    > - 企業ネットワークとしてMicrosoft Defender for Endpointによって識別されなかったネットワークを監視することを選択すると、企業ネットワークの外部でデバイス検出が発生する可能性があるため、自宅やその他の企業以外のデバイスが検出される可能性があります。
    > - ネットワークを無視することを選択すると、そのネットワーク内のデバイスの監視と検出が停止します。 既に検出されたデバイスはインベントリから削除されませんが、更新されなくなり、Defender for Endpoint のデータ保持期間が切れるまで詳細が保持されます。
    > - 企業以外のネットワークを監視することを選択する前に、これを行うアクセス許可があることを確認する必要があります。 <br>

6. 変更を加える必要があることを確認します。

## <a name="explore-devices-in-the-network"></a>ネットワーク内のデバイスを調べる

次の高度なハンティング クエリを使用して、ネットワークの一覧で説明されている各ネットワーク名に関する詳細なコンテキストを取得できます。 クエリには、過去 7 日以内に特定のネットワークに接続されたすべてのオンボードデバイスが一覧表示されます。

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
| summarize arg_max(Timestamp, *) by DeviceId
```

## <a name="get-information-on-device"></a>デバイスに関する情報を取得する

次の高度なハンティング クエリを使用して、特定のデバイスに関する最新の完全な情報を取得できます。

```kusto
DeviceInfo
| where DeviceName == "<device name here>" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId
```

## <a name="see-also"></a>関連項目

- [デバイス検出の概要](device-discovery.md)
- [デバイス検出に関する FAQ](device-discovery-faq.md)
