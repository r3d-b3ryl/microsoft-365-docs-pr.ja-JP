---
title: Mac 上のMicrosoft Defender for Endpointを使用して、望ましくない可能性があるアプリケーションを検出してブロックする
description: macOS でMicrosoft Defender for Endpointを使用して、望ましくない可能性があるアプリケーション (PUA) を検出してブロックします。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, pua, pus
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
ms.openlocfilehash: a0fb8e19dd573da67936892c81cd515b463a7cba
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765749"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a>macOS 上のMicrosoft Defender for Endpointを使用して、望ましくない可能性があるアプリケーションを検出してブロックする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

macOS 上のMicrosoft Defender for Endpointで望ましくない可能性があるアプリケーション (PUA) 保護機能を使用すると、ネットワーク内のエンドポイント上の PUA ファイルを検出してブロックできます。

これらのアプリケーションは、ウイルス、マルウェア、またはその他の種類の脅威とは見なされませんが、パフォーマンスや使用に悪影響を与えるエンドポイントに対してアクションを実行する可能性があります。 PUA は、評判が悪いと見なされるアプリケーションを参照することもできます。

これらのアプリケーションを使用すると、ネットワークがマルウェアに感染するリスクが高まり、マルウェア感染の特定が困難になり、アプリケーションのクリーンアップに IT リソースが無駄になる可能性があります。

## <a name="how-it-works"></a>メカニズム

macOS のMicrosoft Defender for Endpointでは、PUA ファイルを検出して報告できます。 ブロック モードで構成すると、PUA ファイルは検疫に移動されます。

エンドポイントで PUA が検出されると、macOS 上のMicrosoft Defender for Endpointは、通知が無効になっていない限り、ユーザーに通知を表示します。 脅威名には、"Application" という単語が含まれます。

## <a name="configure-pua-protection"></a>PUA 保護を構成する

macOS 上のMicrosoft Defender for Endpointの PUA 保護は、次のいずれかの方法で構成できます。

- **オフ**: PUA 保護は無効です。
- **監査**: PUA ファイルは製品ログに報告されますが、ポータルMicrosoft 365 Defender報告されません。 ユーザーに通知は表示されません。製品によってアクションは実行されません。
- **ブロック**: PUA ファイルは、製品ログとMicrosoft 365 Defender ポータルで報告されます。 ユーザーに通知が表示され、製品によってアクションが実行されます。

> [!WARNING]
> 既定では、PUA 保護は **監査** モードで構成されます。

PUA ファイルの処理方法は、コマンド ラインまたは管理コンソールから構成できます。

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>コマンド ライン ツールを使用して PUA 保護を構成します。

ターミナルで、次のコマンドを実行して PUA 保護を構成します。

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>管理コンソールを使用して PUA 保護を構成します。

企業では、他の製品設定の構成と同様に、JAMF やIntuneなどの管理コンソールから PUA 保護を構成できます。 詳細については、「[macOS でのMicrosoft Defender for Endpointの設定」](mac-preferences.md)トピックの[「脅威の種類の設定](mac-preferences.md#threat-type-settings)」セクションを参照してください。

## <a name="related-topics"></a>関連項目

- [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
