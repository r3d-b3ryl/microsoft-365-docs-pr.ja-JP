---
title: Linux 上のエンドポイント用 Microsoft Defender を使用して、望ましくない可能性のあるアプリケーションを検出およびブロックする
description: Microsoft Defender for Endpoint on Linux を使用して、望ましくない可能性があるアプリケーション (PUA) を検出してブロックします。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, linux, pua, pus
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 73ddc6e4ec4c114a86c88c62287e15e7fa051175
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154796"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a>Linux 上のエンドポイント用 Microsoft Defender を使用して、望ましくない可能性のあるアプリケーションを検出およびブロックする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Defender for Endpoint on Linux の望ましくない可能性のあるアプリケーション (PUA) 保護機能は、ネットワーク内のエンドポイント上の PUA ファイルを検出してブロックできます。

これらのアプリケーションは、ウイルス、マルウェア、その他の種類の脅威とは見なされませんが、パフォーマンスや使用に悪影響を及ぼすエンドポイントに対してアクションを実行する可能性があります。 PUA は、評判が悪いと見なされるアプリケーションも参照できます。

これらのアプリケーションは、ネットワークがマルウェアに感染するリスクを高め、マルウェアの感染を特定しにくくし、アプリケーションのクリーンアップで IT リソースを無駄にする可能性があります。

## <a name="how-it-works"></a>しくみ

Defender for Endpoint on Linux では、PUA ファイルを検出してレポートできます。 ブロック モードで構成すると、PUA ファイルは検疫に移動されます。

エンドポイントで PUA が検出されると、Defender for Endpoint on Linux は脅威履歴に感染の記録を保持します。 履歴は、センター ポータルのMicrosoft 365 Defenderコマンドライン ツール `mdatp` を使用して視覚化できます。 脅威名には"Application" という単語が含まれる。

## <a name="configure-pua-protection"></a>PUA 保護の構成

Defender for Endpoint on Linux の PUA 保護は、次のいずれかの方法で構成できます。

- **Off**: PUA 保護は無効です。
- **監査**: PUA ファイルは製品ログに報告されますが、このログMicrosoft 365 Defender。 感染の記録は脅威の履歴に保存され、製品によるアクションは実行されません。
- **ブロック**: PUA ファイルは、製品ログおよびレポートにMicrosoft 365 Defender。 感染の記録は脅威の履歴に保存され、製品によってアクションが実行されます。

> [!WARNING]
> 既定では、監査モードで PUA 保護 **が構成** されています。

PUA ファイルの処理方法は、コマンド ラインまたは管理コンソールから構成できます。

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>コマンド ライン ツールを使用して PUA 保護を構成します。

ターミナルで、次のコマンドを実行して PUA 保護を構成します。

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>管理コンソールを使用して PUA 保護を構成します。

企業では、他の製品設定の構成方法と同様に、Puppet や Ansible などの管理コンソールから PUA 保護を構成できます。 詳細については、「Defender for [](linux-preferences.md#threat-type-settings) Endpoint on Linux の設定」の「脅威の種類の設定[」セクションを参照](linux-preferences.md)してください。

## <a name="related-articles"></a>関連記事

- [Defender for Endpoint on Linux の基本設定を設定する](linux-preferences.md)
