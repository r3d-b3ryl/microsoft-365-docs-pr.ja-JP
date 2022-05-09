---
title: Linux 上のMicrosoft Defender for Endpointを使用して、望ましくない可能性があるアプリケーションを検出してブロックする
description: Linux 上のMicrosoft Defender for Endpointを使用して、望ましくない可能性があるアプリケーション (PUA) を検出してブロックします。
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, pua, pus
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
ms.openlocfilehash: 03c6f64e7272706262ef622a173e58260468e01b
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168116"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a>Linux 上のMicrosoft Defender for Endpointを使用して、望ましくない可能性があるアプリケーションを検出してブロックする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Defender for Endpoint on Linux の不要と思われるアプリケーション (PUA) 保護機能は、ネットワーク内のエンドポイント上の PUA ファイルを検出してブロックできます。

これらのアプリケーションは、ウイルス、マルウェア、またはその他の種類の脅威とは見なされませんが、パフォーマンスや使用に悪影響を与えるエンドポイントに対してアクションを実行する可能性があります。 PUA は、評判が悪いと見なされるアプリケーションを参照することもできます。

これらのアプリケーションを使用すると、ネットワークがマルウェアに感染するリスクが高まり、マルウェア感染の特定が困難になり、アプリケーションのクリーンアップに IT リソースが無駄になる可能性があります。

## <a name="how-it-works"></a>メカニズム

Defender for Endpoint on Linux では、PUA ファイルを検出して報告できます。 ブロック モードで構成すると、PUA ファイルは検疫に移動されます。

エンドポイントで PUA が検出されると、Defender for Endpoint on Linux は脅威履歴に感染の記録を保持します。 履歴は、Microsoft 365 Defender ポータル ポータルから、またはコマンド ライン ツールを`mdatp`使用して視覚化できます。 脅威名には、"Application" という単語が含まれます。

## <a name="configure-pua-protection"></a>PUA 保護を構成する

Linux 上の Defender for Endpoint の PUA 保護は、次のいずれかの方法で構成できます。

- **オフ**: PUA 保護は無効です。
- **監査**: PUA ファイルは製品ログに報告されますが、Microsoft 365 Defenderには報告されません。 感染の記録は脅威履歴に保存されておらず、製品によってアクションは実行されません。
- **ブロック**: PUA ファイルは、製品ログとMicrosoft 365 Defenderで報告されます。 感染の記録は脅威履歴に保存され、製品によってアクションが実行されます。

> [!WARNING]
> 既定では、PUA 保護は **監査** モードで構成されます。

PUA ファイルの処理方法は、コマンド ラインまたは管理コンソールから構成できます。

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>コマンド ライン ツールを使用して PUA 保護を構成します。

ターミナルで、次のコマンドを実行して PUA 保護を構成します。

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>管理コンソールを使用して PUA 保護を構成します。

企業では、他の製品設定の構成と同様に、Puppet や Ansible などの管理コンソールから PUA 保護を構成できます。 詳細については、「[Defender for Endpoint on Linux の Defender for Endpoint の基本設定を設定する](linux-preferences.md)」の記事の[「脅威の種類の設定](linux-preferences.md#threat-type-settings)」セクションを参照してください。

## <a name="related-articles"></a>関連記事

- [Linux 上の Defender for Endpoint の基本設定を設定する](linux-preferences.md)
