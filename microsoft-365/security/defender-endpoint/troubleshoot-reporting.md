---
title: Microsoft Defender ウイルス対策のレポート ツールに関する問題のトラブルシューティング
description: Update Compliance でMicrosoft Defender ウイルス対策保護状態で報告しようとしたときに発生する一般的な問題を特定して解決する
keywords: トラブルシューティング、エラー、修正、コンプライアンスの更新、oms、監視、レポート、Microsoft Defender ウイルス対策
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: bf65bb13ab45d127bf2302464f1948437e1fe02d
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65417976"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>更新プログラムのコンプライアンスでの Microsoft Defender ウイルス対策レポートのトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

> [!IMPORTANT]
> 2020 年 3 月 31 日に、Update Compliance のMicrosoft Defender ウイルス対策レポート機能が削除されます。 [Microsoft エンドポイント マネージャー](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)を使用してセキュリティ コンプライアンス ポリシーを引き続き定義して確認できます。これにより、セキュリティ機能と更新プログラムを細かく制御できます。

Microsoft Defender ウイルス対策は、Update Compliance で使用できます。 E3、B、F1、VL、Proライセンスの状態が表示されます。 ただし、E5 ライセンスの場合は、[Microsoft Defender for Endpoint ポータル](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)を使用する必要があります。 ライセンス オプションの詳細については、「製品ライセンス オプション[Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)参照してください。

[Windows Analytics Update Compliance を使用して、Microsoft Defender ウイルス対策を使用しているネットワーク内のデバイスまたはエンドポイントの保護状態に関するレポートを取得](/windows/deployment/update/update-compliance-using#wdav-assessment)すると、問題や問題が発生する可能性があります。

通常、問題の最も一般的な指標は次のとおりです。

- 表示される予定だったすべてのデバイスの少数またはサブセットのみが表示されます
- デバイスがまったく表示されない
- 表示されるレポートと情報が古くなっています (数日前より古い)

Update Compliance に関連しないMicrosoft Defender ウイルス対策 サービスに関連する一般的なエラー コードとイベント ID については、「[Microsoft Defender ウイルス対策 イベント](troubleshoot-microsoft-defender-antivirus.md)」を参照してください。

これらの問題をトラブルシューティングするには、次の 3 つの手順があります。

1. すべての前提条件が満たされていることを確認する
2. Windows Defenderクラウドベースのサービスへの接続を確認する
3. サポート ログを送信する

> [!IMPORTANT]
> 通常、デバイスが Update Compliance に表示されるまでに 3 日かかります。

## <a name="confirm-prerequisites"></a>前提条件を確認する

デバイスが Update Compliance に正しく表示されるようにするには、Update Compliance サービスとMicrosoft Defender ウイルス対策の両方の特定の前提条件を満たす必要があります。

>[!div class="checklist"]
>
> - エンドポイントは、唯一のウイルス対策保護アプリとしてMicrosoft Defender ウイルス対策を使用しています。 [他のウイルス対策アプリを使用すると、Microsoft Defender ウイルス対策自体が無効](microsoft-defender-antivirus-compatibility.md)になり、エンドポイントは Update Compliance で報告されません。
> - [クラウド配信保護が有効になっている](enable-cloud-protection-microsoft-defender-antivirus.md)。
> - エンドポイントは[、Microsoft Defender ウイルス対策 クラウドに接続](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)できます
> - エンドポイントがバージョン 1607 以前Windows 10実行されている場合は、[Windows 10診断データを拡張レベルに設定する必要があります](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)。
> - すべての要件が満たされてから 3 日が経過しました

"更新プログラムコンプライアンスでMicrosoft Defender ウイルス対策を使用できます。 E3、B、F1、VL、Proライセンスの状態が表示されます。 ただし、E5 ライセンスの場合は、Microsoft Defender for Endpoint ポータル (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) を使用する必要があります。 ライセンス オプションの詳細については、「Windows 10製品ライセンス オプション」を参照してください。

上記の前提条件がすべて満たされている場合は、次の手順に進んで診断情報を収集し、Microsoft に送信する必要があります。

> [!div class="nextstepaction"]
> [Update Compliance トラブルシューティングの診断データを収集する](collect-diagnostic-data.md)

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="related-topics"></a>関連項目

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender ウイルス対策を展開する](deploy-manage-report-microsoft-defender-antivirus.md)
