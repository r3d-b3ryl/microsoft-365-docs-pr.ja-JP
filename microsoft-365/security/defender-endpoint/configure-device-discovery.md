---
title: デバイス検出の構成
description: 基本または標準の検出を使用して、Microsoft 365 Defender検出を構成する方法について説明します。
keywords: 基本、標準、エンドポイント検出の構成、デバイスの検出
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
ms.openlocfilehash: dc8d03140d19c773e01f6571d69f7593e6e406e8
ms.sourcegitcommit: 2a4dddf7c655b44b17d4fd7f5e1e5d8a6e2b7aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2021
ms.locfileid: "61311844"
---
# <a name="configure-device-discovery"></a>デバイス検出の構成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


検出は、標準モードまたは基本モードで構成できます。 標準オプションを使用して、ネットワーク内のデバイスをアクティブに検索し、エンドポイントの検出を保証し、より豊富なデバイス分類を提供します。

標準検出の実行に使用するデバイスの一覧をカスタマイズできます。 この機能をサポートしているすべてのオンボード デバイス (現在は Windows 10 デバイスと Windows 2019 デバイスのみ) で標準検出を有効にするか、デバイス タグを指定してデバイスのサブセットまたはサブセットを選択できます。

## <a name="set-up-device-discovery"></a>デバイス検出のセットアップ

デバイスの検出を設定するには、ポータルで次の<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">構成Microsoft 365 Defenderします</a>。

[デバイスの検出 **設定**  >  **に移動する**

1. オンボード デバイスで使用する検出モードとして Basic を構成する場合は、[基本] を選択し、[保存] を **選択します。**
2. 標準検出を使用する場合は、アクティブなプロブに使用するデバイスを選択します。デバイス タグを指定して、すべてのデバイスまたはサブセットで使用し、[保存] を選択 **します**。

> [!NOTE]
>標準検出では、さまざまな PowerShell スクリプトを使用して、ネットワーク内のデバイスをアクティブにプローブします。 これらの PowerShell スクリプトは Microsoft 署名済みで、次の場所から実行されます `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` 。 たとえば、`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1` などです。

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>デバイスが標準検出でアクティブにプローブされるのを除外する

ネットワーク上にアクティブにスキャンすべきではないデバイス (たとえば、別のセキュリティ ツールでハニーポットとして使用されるデバイス) がある場合は、除外リストを定義してスキャンを防止することもできます。 デバイスは、基本検出モードを使用して検出できます。また、マルチキャスト検出の試みによっても検出できます。 これらのデバイスは受動的に検出されますが、アクティブにプローブされません。

除外するデバイスは、[除外] ページ **で構成** できます。

## <a name="select-networks-to-monitor"></a>監視するネットワークの選択

 Microsoft Defender for Endpoint は、ネットワークを分析し、監視が必要な企業ネットワークか、無視できる非企業ネットワークかどうかを判断します。 通常、企業ネットワークは監視対象として選択されます。 ただし、オンボードデバイスが見つかった企業以外のネットワークを監視することで、この決定を上書きできます。

監視するネットワークを指定することで、デバイスの検出を実行できる場所を構成できます。 ネットワークを監視すると、デバイス検出をそのネットワークで実行できます。

デバイス検出を実行できるネットワークの一覧が、[監視対象のネットワーク] **ページに表示** されます。

> [!NOTE]
> 一覧には、企業ネットワークとして識別されたネットワークが表示されます。 50 未満のネットワークが企業ネットワークとして識別された場合、リストには、オンボードデバイスが最も多い最大 50 のネットワークが表示されます。

監視対象のネットワークの一覧は、過去 7 日間にネットワークに表示されたデバイスの総数に基づいて並べ替えます。

フィルターを適用して、次のネットワーク検出状態を表示できます。

- **監視対象のネットワーク** - デバイス検出が実行されるネットワーク。
- **無視されたネットワーク** - このネットワークは無視され、デバイスの検出は実行されません。
- **All** - 監視対象ネットワークと無視されたネットワークの両方が表示されます。

### <a name="configure-the-network-monitor-state"></a>ネットワーク モニターの状態を構成する

デバイス検出の実行場所を制御します。 監視対象のネットワークは、デバイスの検出が実行される場所であり、通常は企業ネットワークです。 ネットワークを無視するか、状態を変更した後の最初の検出分類を選択するように選択できます。

最初の検出分類を選択すると、既定のシステムで作成されたネットワーク モニター状態が適用されます。 既定のシステム製のネットワーク モニター状態を選択すると、企業として識別され、監視され、非企業として識別されたネットワークは自動的に無視されます。

1. [デバイス **設定 >] を選択します**。
2. [監視 **対象のネットワーク] を選択します**。
3. ネットワークの一覧を表示します。
4. ネットワーク名の横にある 3 つのドットを選択します。
5. 初期検出分類を監視、無視、または使用するかどうかを選択します。

    > [!WARNING]
    >
    > - Microsoft Defender for Endpoint によって企業ネットワークとして識別されていないネットワークを監視すると、企業ネットワークの外部でデバイスの検出が発生し、自宅や他の企業以外のデバイスを検出する可能性があります。
    > - ネットワークを無視すると、そのネットワーク内のデバイスの監視と検出が停止します。 既に検出されたデバイスはインベントリから削除されませんが、更新されなくなるので、Defender for Endpoint のデータ保持期間が経過するまで詳細が保持されます。
    > - 企業以外のネットワークを監視する前に、その権限を持っている必要があります。 <br>

6. 変更を行う必要があります。

## <a name="explore-devices-in-the-network"></a>ネットワーク内のデバイスを探索する

次の高度な検索クエリを使用して、ネットワーク リストで説明されている各ネットワーク名に関するコンテキストを取得できます。 クエリには、過去 7 日以内に特定のネットワークに接続されたオンボード デバイスすべてが一覧表示されます。

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

## <a name="get-information-on-device"></a>デバイスの情報を取得する

次の高度な検索クエリを使用して、特定のデバイスの最新の完全な情報を取得できます。

```kusto
DeviceInfo
| where DeviceName == "<device name here>" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId
```

## <a name="see-also"></a>関連項目

- [デバイス検出の概要](device-discovery.md)
- [デバイスの検出に関するよくある質問](device-discovery-faq.md)
