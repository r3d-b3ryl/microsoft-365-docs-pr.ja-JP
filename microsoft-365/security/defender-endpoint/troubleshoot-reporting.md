---
title: レポート ツールに関する問題のトラブルシューティングを行Microsoft Defender ウイルス対策
description: 更新コンプライアンスで保護状態を報告しようとするときに、一般的なMicrosoft Defender ウイルス対策を特定して解決する
keywords: トラブルシューティング、エラー、修正、更新コンプライアンス、oms、監視、レポート、Microsoft Defender ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6574b19427814b53e131f72f708e534f3b29554d
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2021
ms.locfileid: "59399372"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>更新プログラムのコンプライアンスでの Microsoft Defender ウイルス対策レポートのトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> 2020 年 3 月 31 日に、更新Microsoft Defender ウイルス対策レポート機能が削除されます。 セキュリティの機能と更新プログラムを細かく制御できる Microsoft エンドポイント マネージャー を使用して、引[き続き](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)セキュリティ コンプライアンス ポリシーを定義および確認できます。

更新プログラムのコンプライアンスMicrosoft Defender ウイルス対策を使用できます。 E3、B、F1、VL、およびライセンスの状態Pro表示されます。 ただし、E5 ライセンスの場合は [、Microsoft Defender for Endpoint ポータルを使用する必要があります](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。 ライセンス オプションの詳細については、「製品[ライセンス オプションWindows 10を参照してください](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)。

[Windows Analytics Update Compliance](/windows/deployment/update/update-compliance-using#wdav-assessment)を使用して、Microsoft Defender ウイルス対策 を使用しているネットワーク内のデバイスまたはエンドポイントの保護状態に関するレポートを取得すると、問題や問題が発生する可能性があります。

通常、問題の最も一般的なインジケーターは次のとおりです。

- 表示を期待していたすべてのデバイスの数またはサブセットのみが表示されます。
- デバイスが一切表示されない
- 表示されるレポートと情報が古くなっている (数日以上前)

更新コンプライアンスに関連しない Microsoft Defender ウイルス対策 サービスに関連する一般的なエラー コードとイベントの MICROSOFT DEFENDER ウイルス対策[を参照してください](troubleshoot-microsoft-defender-antivirus.md)。

これらの問題のトラブルシューティングには、次の 3 つの手順があります。

1. すべての前提条件を満たしていることを確認する
2. クラウド ベースのサービスへの接続Windows Defender確認する
3. サポート ログの送信

> [!IMPORTANT]
> 通常、デバイスが更新コンプライアンスに表示され始めるには 3 日かかる。

## <a name="confirm-prerequisites"></a>前提条件の確認

デバイスが更新コンプライアンスに適切に表示するには、更新コンプライアンス サービスと更新プログラムの両方の前提条件を満たす必要Microsoft Defender ウイルス対策。

>[!div class="checklist"]
>
> - エンドポイントは、Microsoft Defender ウイルス対策ウイルス対策保護アプリとして使用しています。 [他のウイルス対策アプリを使用すると、Microsoft Defender ウイルス対策](microsoft-defender-antivirus-compatibility.md)が無効にされ、エンドポイントは更新コンプライアンスで報告されません。
> - [クラウド配信の保護が有効になっています](enable-cloud-protection-microsoft-defender-antivirus.md)。
> - エンドポイントはクラウド[にMicrosoft Defender ウイルス対策できます](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - エンドポイントがバージョン 1607 Windows 10前に実行されている場合、Windows 10データを拡張[レベルに設定する必要があります](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)。
> - すべての要件が満たされたのは 3 日間です。

"更新プログラムのコンプライアンスMicrosoft Defender ウイルス対策を使用できます。 E3、B、F1、VL、およびライセンスの状態Pro表示されます。 ただし、E5 ライセンスの場合は、Microsoft Defender for Endpoint ポータル (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) を使用する必要があります。 ライセンス オプションの詳細については、「製品Windows 10」を参照してください。

上記の前提条件が満たされている場合は、次の手順に進み、診断情報を収集して送信する必要があります。

> [!div class="nextstepaction"]
> [更新コンプライアンスのトラブルシューティングの診断データを収集する](collect-diagnostic-data.md)

## <a name="related-topics"></a>関連項目

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [展開Microsoft Defender ウイルス対策](deploy-manage-report-microsoft-defender-antivirus.md)
