---
title: ダウンロード可能な準備状況の評価チェック
description: 必要なエンドポイントを含む、デバイスとネットワークの設定を確認します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49922021"
---
# <a name="downloadable-readiness-assessment-checker"></a>ダウンロード可能な準備状況の評価チェック

Microsoft マネージド デスクトップで動作するには、デバイスがハードウェアと設定に関する特定の要件を満たしている必要があります。 また、各デバイスが主要なエンドポイントに到達できる必要があります。 このツールをダウンロードして実行し、HTML レポートを取得し、結果を表示して、アクションを実行します。 ツールとサポート ファイルをダウンロードし、Microsoft マネージド デスクトップに登録する各デバイスで手動で実行する必要があります。

チェックごとに、ツールは次の 3 つの結果のいずれかを報告します。


|結果  |意味  |
|---------|---------|
|準備完了     | 登録を完了する前に、何もする必要はありません。        |
|アドバイザリ    | 登録とユーザーに最適なエクスペリエンスを得る場合は、ツールの手順に従ってください。 登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。        |
|使用不可能 | *これらの問題を* 解決しない場合、登録は失敗します。 ツールの手順に従って解決します。        |

## <a name="obtain-the-checker"></a>チェッカーを取得する

.zip ファイルをダウンロードします https://aka.ms/mmddratoolv0 。

> [!NOTE]
> ツールを実行するユーザーは、ツールを実行しているデバイスに対するローカル管理者権限を持っている必要があります。

 次に、次の手順に従ってツールを実行します。

1. ダウンロードした .zip ファイルを、確認する各デバイスにコピーします。
2. 圧縮ダウンロード内のすべてのファイルを抽出します。
3. Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.
4. ユーザー アクセス制御のプロンプトが表示されたら、[はい] を選択 **します**。 ツールが実行され、既定のブラウザーでレポートが開きます。

また、.zip アーカイブをダウンロードして共有の場所に抽出し、各 **デバイス** Microsoft.MMD.DeviceReadinessAssessmentTool.exeにアクセスして、ローカルで実行することもできます。


## <a name="checks"></a>チェック

ダウンロード可能なツールは、デバイスとネットワークに関連する次の項目をチェックします。

### <a name="hardware"></a>ハードウェア

デバイスが Microsoft マネージド デスクトップで動作するには、特定のハードウェア要件を満たす必要があります。 現在、登録 [できるのは特定の](../service-description/device-list.md) 承認済みデバイスのみです。 

デバイスがチェックに失敗した場合、Microsoft マネージド デスクトップと互換性がありません。

### <a name="network-endpoints"></a>ネットワーク エンドポイント

デバイスは、Microsoft マネージド デスクトップで [動作するために](network.md) 、いくつかの主要なエンドポイントにアクセスできます。

ツールで準備ができていない結果 **が** 報告された場合は、詳細なレポートを参照して、到達不能なエンドポイントを確認します。 次に、ファイアウォールまたは他のネットワーク設定を調整して、それらのエンドポイントに到達可能にします。

### <a name="other-settings"></a>その他の設定

#### <a name="enterprise-wi-fi-profiles"></a>エンタープライズ Wi-Fi プロファイル

アドバイザリ **の結果** は、証明書とプロファイルが正常に動作する必要がある Wi-Fi プロファイルを使用しているという意味です。 詳細については、「証明書と [Wi-Fi/VPN プロファイルを展開する」を参照してください](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)。

#### <a name="lan-profiles"></a>LAN プロファイル

アドバイザリ **の結果** は、証明書とプロファイルが正常に動作する必要がある LAN を持っているという意味です。 詳細については [、「Microsoft マネージド デスクトップの証明書とネットワーク プロファイルを準備する」を参照してください](certs-wifi-lan.md)。

#### <a name="vpn-profiles"></a>VPN プロファイル

アドバイザリ **の結果** は、仮想プライベート ネットワーク (VPN) を使用しているという意味です。 Microsoft Intune と統合された証明書を展開する VPN プロファイルを作成します。 詳細については [、「Microsoft マネージド デスクトップの証明書とネットワーク プロファイルを準備する」を参照してください](certs-wifi-lan.md)。

#### <a name="mapped-drives"></a>マップされたドライブ

アドバイザリ **の結果** は、マップされたドライブがいくつかあるという意味ですが、推奨されません。 詳細については、「Microsoft マネージド デスクトップ用 [にマップされたドライブを準備する」を参照してください](mapped-drives.md)。

#### <a name="print-queues"></a>印刷キュー

アドバイザリ **の結果** は、未処理の印刷キューがいくつかあるという意味ですが、お勧めしません。 1 つのソリューションは、クラウド印刷を使用する方法です。 詳細については、「Microsoft マネージド [デスクトップの印刷リソースを準備する」を参照してください](printing.md)。

#### <a name="proxies"></a>プロキシ

アドバイザリ **の結果** は、プロキシ サーバーが使用されているという意味です。 詳細については、「Microsoft マネージド [デスクトップのネットワーク構成」を参照してください](network.md)。

