---
title: iOS 機能に Microsoft Defender for Endpoint を展開する
description: 登録されていない iOS デバイスに Microsoft Defender for Endpoint を展開する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, ios, configure, features, ios
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7057de56de516843fa91e87a50d56e03a2d88e50
ms.sourcegitcommit: 835dcaf5d5e0b485dc3ac485ded8943046afe36c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2021
ms.locfileid: "59941947"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-unenrolled-ios-devices"></a>登録されていない iOS デバイスに Microsoft Defender for Endpoint を展開する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> iOS のエンドポイントの Defender は、Web 保護機能を提供するために VPN を使用します。 これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。

## <a name="configure-microsoft-defender-for-endpoint-risk-signals-in-app-protection-policy-mam"></a>アプリ保護ポリシー (MAM) で Microsoft Defender for Endpoint リスクシグナルを構成する

Microsoft Defender for Endpoint は、iOS/iPadOS のアプリ保護ポリシー (APP、 MAM とも呼ばれる) で使用される脅威信号を送信するように構成できます。 この機能を使用すると、Microsoft Defender for Endpoint を使用して、登録されていないデバイスから企業データへのアクセスを保護することもできます。

### <a name="pre-requisites"></a>前提条件

1. **コネクタが有効になっているか確認します**。 <br> 統合セキュリティ [コンソールで](https://security.microsoft.com)、[エンドポイントの高度な **機能** 設定に移動し、接続が有効Microsoft Intune  >    >  **確認** します。
2. **Intune ポータルでコネクタが有効になっているか確認します**。 <br> [Microsoft Endpoint manager 管理センターで、[](https://go.microsoft.com/fwlink/?linkid=2109431)エンドポイント セキュリティ] [エンドポイント用 Microsoft Defender] に移動し、[接続] 状態  >  が有効になっているか確認します。

Microsoft Defender for Endpoint を使用してアプリ保護ポリシーをセットアップするには、次の手順を使用します。

1. Microsoft Defender for Endpoint への Microsoft エンドポイント マネージャーテナントからの接続を設定します。 [Microsoft Endpoint](https://go.microsoft.com/fwlink/?linkid=2109431)Manager 管理センターで、[テナント管理コネクタとトークン Microsoft Defender for Endpoint (クロス プラットフォーム) またはエンドポイント セキュリティ Microsoft Defender for Endpoint (セットアップ] の下) に移動し、[アプリ保護ポリシー 設定 for \>  \>   \>  **iOS]** のトグルをオンにします。
1. **[保存]** を選択します。 [接続の状態 **] が [有効]** に設定されている必要 **があります**。
1. アプリ保護ポリシーを作成する: Microsoft Defender for Endpoint Connector のセットアップが完了したら、[アプリアプリ保護ポリシー] ([ポリシー] の下) に移動して、新しいポリシーを作成するか、既存のポリシーを \> 更新します。
1. 組織がポリシーに必要とするプラットフォーム、 **アプリ、データ** 保護、アクセス要件の設定を選択します。
1. [ **条件付き起動** \> **デバイスの条件**] で、[最大許可デバイスの脅威レベル **] という設定が表示されます**。 これは、Low、Medium、High、または Secured のどちらかに構成する必要があります。 使用できるアクションは、[アクセスのブロック] **または [** データの **ワイプ] になります**。 この設定を有効にする前に、コネクタをセットアップする情報ダイアログが表示される場合があります。 コネクタが既にセットアップされている場合は、このダイアログは無視できます。
1. [割り当て] で終了し、ポリシーを保存します。

MAM またはアプリ保護ポリシーの詳細については [、「iOS アプリ保護ポリシー設定」を参照してください](/mem/intune/apps/app-protection-policy-settings-ios)。

## <a name="deploy-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>MICROSOFT Defender for Endpoint for MAM または登録されていないデバイスに展開する

Microsoft Defender for Endpoint on iOS では、アプリ保護ポリシーのシナリオを有効にし、Apple アプリ ストアで利用できます。

アプリ保護ポリシーが、Microsoft Defender for Endpoint からのデバイス リスク信号を含むアプリ用に構成されている場合、そのようなアプリを使用する場合、ユーザーは Microsoft Defender for Endpoint をインストールするようにリダイレクトされます。 また、ユーザーは Apple アプリ ストアから直接アプリの最新バージョンをインストールすることもできます。
