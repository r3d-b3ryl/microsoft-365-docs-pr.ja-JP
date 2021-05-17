---
title: ダウンロード可能な準備状況の評価チェック
description: 必要なエンドポイントを含むデバイスとネットワークの設定を確認する
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581036"
---
# <a name="downloadable-readiness-assessment-checker"></a>ダウンロード可能な準備状況の評価チェック

Microsoft Managed Desktop とうまく機能するには、デバイスがハードウェアと設定に関する特定の要件を満たしている必要があります。 また、各デバイスが主要なエンドポイントに到達できる必要があります。 このツールをダウンロードして実行して、HTML レポートを取得し、結果を表示し、アクションを実行します。 ツールとサポート ファイルをダウンロードし、Microsoft Managed Desktop に登録する各デバイスで手動で実行する必要があります。

チェックごとに、ツールは次の 3 つの結果のいずれかを報告します。


|結果  |意味  |
|---------|---------|
|準備完了     | 登録を完了する前に、アクションは必要ありません。        |
|アドバイザリ    | 登録とユーザーの最適なエクスペリエンスを得るには、ツールの手順に従います。 登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。        |
|使用不可能 | *これらの問題を* 解決しない場合、登録は失敗します。 ツールの手順に従って解決します。        |

## <a name="obtain-the-checker"></a>チェッカーを取得する

から.zipファイルをダウンロードします https://aka.ms/mmddratoolv0 。

> [!NOTE]
> ツールを実行しているユーザーは、そのツールを実行しているデバイスに対するローカル管理者権限を持っている必要があります。

 次に、次の手順に従ってツールを実行します。

1. ダウンロードしたファイルを.zipする各デバイスにコピーします。
2. 圧縮されたダウンロード内のすべてのファイルを抽出します。
3. [実行 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe] をクリックします**。
4. [ユーザー アクセス制御] プロンプトが表示されたら、[はい] を **選択します**。 ツールが実行され、既定のブラウザーでレポートが開きます。

また、共有の場所に.zipアーカイブをダウンロードして抽出し、各Microsoft.MMD.DeviceReadinessAssessmentTool.exeからアクセスし、ローカルで実行することもできます。


## <a name="checks"></a>チェック

ダウンロード可能なツールは、次のデバイスおよびネットワーク関連のアイテムをチェックします。

### <a name="hardware"></a>ハードウェア

Microsoft Managed Desktop を使用するには、デバイスが特定のハードウェア要件を満たしている必要があります。 現時点では、特定 [の承認済みデバイス](../service-description/device-list.md) のみ登録が許可されています。 

デバイスがチェックに失敗した場合、Microsoft Managed Desktop と互換性がありません。

### <a name="network-endpoints"></a>ネットワーク エンドポイント

デバイスは、Microsoft Managed Desktop [で動作](network.md) するいくつかの主要なエンドポイントに多く到達できます。

ツールが [準備完了] **の結果を** 報告する場合は、詳細なレポートを参照して、到達不能だったエンドポイントを確認します。 その後、ファイアウォールまたは他のネットワーク設定を調整して、それらのエンドポイントに到達可能にしてください。

### <a name="other-settings"></a>その他の設定

#### <a name="enterprise-wi-fi-profiles"></a>エンタープライズ Wi-Fi プロファイル

アドバイザリ **の結果** は、証明書とプロファイルが適切に動作する必要があるいくつかの Wi-Fi プロファイルを使用しているという意味です。 詳細については、「証明書の [展開」および「Wi-Fi/VPN プロファイル」を参照してください](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)。

#### <a name="lan-profiles"></a>LAN プロファイル

アドバイザリ **の結果** は、証明書とプロファイルが適切に動作する必要がある LAN を持っているという意味です。 詳細については [、「Prepare certificates and network profiles for Microsoft Managed Desktop」を参照してください](certs-wifi-lan.md)。

#### <a name="vpn-profiles"></a>VPN プロファイル

アドバイザリ **の結果** は、仮想プライベート ネットワーク (VPN) を使用しているという意味です。 Microsoft Intune と統合された証明書を展開する VPN プロファイルを作成します。 詳細については [、「Prepare certificates and network profiles for Microsoft Managed Desktop」を参照してください](certs-wifi-lan.md)。

#### <a name="mapped-drives"></a>マップされたドライブ

アドバイザリ **の結果** は、マップされたドライブがいくつかあるという意味で、推奨されません。 詳細については、「マップされたドライブ [を Microsoft Managed Desktop 用に準備する」を参照してください](mapped-drives.md)。

#### <a name="print-queues"></a>印刷キュー

アドバイザリ **の結果** は、未処理の印刷キューがいくつかあるという意味で、推奨されません。 1 つの解決策は、クラウド印刷を使用する方法です。 詳細については [、「Microsoft Managed Desktop の印刷リソースを準備する」を参照してください](printing.md)。

#### <a name="proxies"></a>プロキシ

アドバイザリ **の結果** は、プロキシ サーバーが使用されているという意味です。 詳細については [、「Microsoft Managed Desktop のネットワーク構成」を参照してください](network.md)。

