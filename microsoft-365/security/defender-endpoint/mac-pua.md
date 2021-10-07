---
title: Microsoft Defender for Endpoint on Mac で望ましくない可能性のあるアプリケーションを検出してブロックする
description: Microsoft Defender on Endpoint for Mac を使用して、望ましくない可能性があるアプリケーション (PUA) を検出してブロックします。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, pua, pus
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 61ff0fd32deb6f7fb607be6f723b990da1fa4846
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169817"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a>MacOS 上のエンドポイント用 Microsoft Defender を使用して、望ましくない可能性のあるアプリケーションを検出およびブロックする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

macOS 上の Microsoft Defender for Endpoint の望ましくない可能性のあるアプリケーション (PUA) 保護機能は、ネットワーク内のエンドポイント上の PUA ファイルを検出してブロックできます。

これらのアプリケーションは、ウイルス、マルウェア、その他の種類の脅威とは見なされませんが、パフォーマンスや使用に悪影響を及ぼすエンドポイントに対してアクションを実行する可能性があります。 PUA は、評判が悪いと見なされるアプリケーションも参照できます。

これらのアプリケーションは、ネットワークがマルウェアに感染するリスクを高め、マルウェアの感染を特定しにくくし、アプリケーションのクリーンアップで IT リソースを無駄にする可能性があります。

## <a name="how-it-works"></a>しくみ

Microsoft Defender for Endpoint on macOS では、PUA ファイルを検出して報告できます。 ブロック モードで構成すると、PUA ファイルは検疫に移動されます。

エンドポイントで PUA が検出されると、通知が無効にされていない限り、macOS 上の Microsoft Defender for Endpoint はユーザーに通知を表示します。 脅威名には"Application" という単語が含まれる。

## <a name="configure-pua-protection"></a>PUA 保護の構成

macOS 上の Microsoft Defender for Endpoint の PUA 保護は、次のいずれかの方法で構成できます。

- **Off**: PUA 保護は無効です。
- **監査**: PUA ファイルは製品ログに報告されますが、このポータルMicrosoft 365 Defenderされません。 ユーザーに通知は表示されません。また、製品によるアクションは実行されません。
- **ブロック**: PUA ファイルは、製品ログとポータルでMicrosoft 365 Defenderされます。 ユーザーに通知が表示され、製品によってアクションが実行されます。

> [!WARNING]
> 既定では、監査モードで PUA 保護 **が構成** されています。

PUA ファイルの処理方法は、コマンド ラインまたは管理コンソールから構成できます。

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>コマンド ライン ツールを使用して PUA 保護を構成します。

ターミナルで、次のコマンドを実行して PUA 保護を構成します。

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>管理コンソールを使用して PUA 保護を構成します。

企業では、他の製品設定の構成方法と同様に、JAMF や Intune などの管理コンソールから PUA 保護を構成できます。 詳細については、「MacOS[](mac-preferences.md#threat-type-settings)での Microsoft Defender for Endpoint の設定」の「[脅威の種類の設定」セクションを参照](mac-preferences.md)してください。

## <a name="related-topics"></a>関連トピック

- [macOS のエンドポイント用 Microsoft Defender の基本設定を設定する](mac-preferences.md)
