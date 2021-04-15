---
title: Microsoft Defender AV のレポート ツールに関する問題のトラブルシューティング
description: Microsoft Defender AV 保護の状態を更新コンプライアンスで報告しようとするときに一般的な問題を特定して解決する
keywords: トラブルシューティング、エラー、修正、更新コンプライアンス、oms、モニター、レポート、Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 50136c620450861c41513650f27bf24fc782e968
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764533"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>更新プログラムのコンプライアンスで Microsoft Defender ウイルス対策レポートのトラブルシューティングを行う

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> 2020 年 3 月 31 日、更新コンプライアンスの Microsoft Defender ウイルス対策レポート機能が削除されます。 Microsoft [Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)を使用して、セキュリティ コンプライアンス ポリシーを引き続き定義および確認できます。これにより、セキュリティ機能と更新プログラムを細かく制御できます。

Microsoft Defender ウイルス対策と更新コンプライアンスを使用できます。 E3、B、F1、VL、Pro のライセンスの状態が表示されます。 ただし、E5 ライセンスの場合は [、Microsoft Defender for Endpoint ポータルを使用する必要があります](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。 ライセンス オプションの詳細については [、「Windows 10 製品ライセンス オプション」を参照してください](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)。

[Windows Analytics Update Compliance](/windows/deployment/update/update-compliance-using#wdav-assessment)を使用して、Microsoft Defender Antivirus を使用しているネットワーク内のデバイスまたはエンドポイントの保護状態に関するレポートを取得すると、問題や問題が発生する可能性があります。

通常、問題の最も一般的なインジケーターは次のとおりです。
- 表示を期待していたすべてのデバイスの数またはサブセットのみが表示されます。
- デバイスが一切表示されない
- 表示されるレポートと情報が古くなっている (数日以上前)

更新コンプライアンスに関連しない Microsoft Defender ウイルス対策サービスに関連する一般的なエラー コードとイベントの ID については、「Microsoft Defender Antivirus イベント」 [を参照してください](troubleshoot-microsoft-defender-antivirus.md)。 

これらの問題のトラブルシューティングには、次の 3 つの手順があります。

1. すべての前提条件を満たしていることを確認する
2. クラウド ベース サービスへの接続Windows Defender確認する
3. サポート ログの送信

>[!IMPORTANT]
>通常、デバイスが更新コンプライアンスに表示され始めるには 3 日かかる。


## <a name="confirm-prerequisites"></a>前提条件の確認

デバイスが更新コンプライアンスに適切に表示するには、更新コンプライアンス サービスと Microsoft Defender ウイルス対策の両方に関する特定の前提条件を満たす必要があります。

>[!div class="checklist"]
>- エンドポイントは、Microsoft Defender Antivirus を唯一のウイルス対策保護アプリとして使用しています。 [他のウイルス対策アプリを使用すると、Microsoft Defender AV](microsoft-defender-antivirus-compatibility.md) はそれ自体を無効にし、エンドポイントは Update Compliance で報告されません。
> - [クラウド配信の保護が有効になっています](enable-cloud-protection-microsoft-defender-antivirus.md)。
> - エンドポイントは Microsoft Defender AV クラウド [に接続できます](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - エンドポイントで Windows 10 バージョン 1607 以前を実行している場合は、Windows 10 診断データを拡張レベル [に設定する必要があります](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)。
> - すべての要件が満たされたのは 3 日間です。

"Microsoft Defender ウイルス対策と更新プログラムのコンプライアンスを使用できます。 E3、B、F1、VL、Pro のライセンスの状態が表示されます。 ただし、E5 ライセンスの場合は、Microsoft Defender for Endpoint ポータル ( を使用する必要があります https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) 。 ライセンス オプションの詳細については、「Windows 10 製品ライセンス オプション」を参照してください。

上記の前提条件が満たされている場合は、次の手順に進み、診断情報を収集して送信する必要があります。

> [!div class="nextstepaction"]
> [更新コンプライアンスのトラブルシューティングの診断データを収集する](collect-diagnostic-data.md)  

## <a name="related-topics"></a>関連項目

- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender ウイルス対策の展開](deploy-manage-report-microsoft-defender-antivirus.md)