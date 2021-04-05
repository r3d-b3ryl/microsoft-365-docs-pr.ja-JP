---
title: Microsoft Defender ATP for Linux を使用して望ましくない可能性のあるアプリケーションを検出およびブロックする
description: Microsoft Defender ATP for Linux を使用して、望ましくない可能性があるアプリケーション (PUA) を検出してブロックします。
keywords: microsoft、Defender、atp、Linux、pua、pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a6f2e2057ca78cb0e1114ed86829cd931dc1cd2b
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587553"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender for Endpoint for Linux を使用して、望ましくない可能性のあるアプリケーションを検出してブロックする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Defender for Endpoint for Linux の望ましくない可能性のあるアプリケーション (PUA) 保護機能は、ネットワーク内のエンドポイント上の PUA ファイルを検出してブロックできます。

これらのアプリケーションは、ウイルス、マルウェア、その他の種類の脅威とは見なされませんが、パフォーマンスや使用に悪影響を及ぼすエンドポイントに対してアクションを実行する可能性があります。 PUA は、評判が悪いと見なされるアプリケーションも参照できます。

これらのアプリケーションは、ネットワークがマルウェアに感染するリスクを高め、マルウェアの感染を特定しにくくし、アプリケーションのクリーンアップで IT リソースを無駄にする可能性があります。

## <a name="how-it-works"></a>メカニズム

Defender for Endpoint for Linux では、PUA ファイルを検出して報告できます。 ブロック モードで構成すると、PUA ファイルは検疫に移動されます。

エンドポイントで PUA が検出されると、Defender for Endpoint for Linux は脅威履歴に感染の記録を保持します。 履歴は、Microsoft Defender セキュリティ センター ポータルまたはコマンド ライン ツール `mdatp` を使用して視覚化できます。 脅威名には"Application" という単語が含まれる。

## <a name="configure-pua-protection"></a>PUA 保護の構成

Defender for Endpoint for Linux の PUA 保護は、次のいずれかの方法で構成できます。

- **Off**: PUA 保護は無効です。
- **監査**: PUA ファイルは製品ログに報告されますが、Microsoft Defender セキュリティ センターでは報告されません。 感染の記録は脅威の履歴に保存され、製品によるアクションは実行されません。
- **ブロック**: PUA ファイルは、製品ログと Microsoft Defender セキュリティ センターで報告されます。 感染の記録は脅威の履歴に保存され、製品によってアクションが実行されます。

>[!WARNING]
>既定では、監査モードで PUA 保護 **が構成** されています。

PUA ファイルの処理方法は、コマンド ラインまたは管理コンソールから構成できます。

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>コマンド ライン ツールを使用して PUA 保護を構成します。

ターミナルで、次のコマンドを実行して PUA 保護を構成します。

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>管理コンソールを使用して PUA 保護を構成します。

企業では、他の製品設定の構成方法と同様に、Puppet や Ansible などの管理コンソールから PUA 保護を構成できます。 詳細については、「Defender for [](linux-preferences.md#threat-type-settings) Endpoint for Linux の設定」の「脅威の種類の設定[」セクションを参照](linux-preferences.md)してください。

## <a name="related-articles"></a>関連記事

- [Defender for Endpoint for Linux の基本設定を設定する](linux-preferences.md)
