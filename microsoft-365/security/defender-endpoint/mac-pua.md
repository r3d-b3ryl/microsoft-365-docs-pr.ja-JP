---
title: Microsoft Defender ATP for Mac を使用して望ましくない可能性のあるアプリケーションを検出およびブロックする
description: Microsoft Defender ATP for Mac を使用して、望ましくない可能性があるアプリケーション (PUA) を検出してブロックします。
keywords: microsoft、Defender、atp、mac、pua、pus
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6e65e847403160d24eac04a553ca16a46314e33d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187423"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-mac"></a>Microsoft Defender for Endpoint for Mac で望ましくない可能性のあるアプリケーションを検出してブロックする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Microsoft Defender for Endpoint for Mac の望ましくない可能性のあるアプリケーション (PUA) 保護機能は、ネットワーク内のエンドポイント上の PUA ファイルを検出してブロックできます。

これらのアプリケーションは、ウイルス、マルウェア、その他の種類の脅威とは見なされませんが、パフォーマンスや使用に悪影響を及ぼすエンドポイントに対してアクションを実行する可能性があります。 PUA は、評判が悪いと見なされるアプリケーションも参照できます。

これらのアプリケーションは、ネットワークがマルウェアに感染するリスクを高め、マルウェアの感染を特定しにくくし、アプリケーションのクリーンアップで IT リソースを無駄にする可能性があります。

## <a name="how-it-works"></a>メカニズム

Microsoft Defender for Endpoint for Mac では、PUA ファイルを検出して報告できます。 ブロック モードで構成すると、PUA ファイルは検疫に移動されます。

エンドポイントで PUA が検出されると、Microsoft Defender for Endpoint for Mac は、通知が無効にされていない限り、ユーザーに通知を表示します。 脅威名には"Application" という単語が含まれる。

## <a name="configure-pua-protection"></a>PUA 保護の構成

Microsoft Defender for Endpoint for Mac の PUA 保護は、次のいずれかの方法で構成できます。

- **Off**: PUA 保護は無効です。
- **監査**: PUA ファイルは製品ログに報告されますが、Microsoft Defender セキュリティ センターでは報告されません。 ユーザーに通知は表示されません。また、製品によるアクションは実行されません。
- **ブロック**: PUA ファイルは、製品ログと Microsoft Defender セキュリティ センターで報告されます。 ユーザーに通知が表示され、製品によってアクションが実行されます。

>[!WARNING]
>既定では、監査モードで PUA 保護 **が構成** されています。

PUA ファイルの処理方法は、コマンド ラインまたは管理コンソールから構成できます。

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>コマンド ライン ツールを使用して PUA 保護を構成します。

ターミナルで、次のコマンドを実行して PUA 保護を構成します。

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>管理コンソールを使用して PUA 保護を構成します。

企業では、他の製品設定の構成方法と同様に、JAMF や Intune などの管理コンソールから PUA 保護を構成できます。 詳細については、「Microsoft Defender [](mac-preferences.md#threat-type-settings) for Endpoint for Mac の設定」の「脅威の種類の設定[」セクションを参照](mac-preferences.md)してください。

## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpoint for Mac の基本設定を設定する](mac-preferences.md)
