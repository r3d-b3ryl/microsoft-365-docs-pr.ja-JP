---
title: Microsoft Defender for Endpointで Microsoft Defender for IoT 統合を有効にする
description: Microsoft Defender for IoT 統合を有効にして、MDE がデプロイされていないネットワークの領域で IoT/OT デバイスに焦点を当てた可視性を得る
keywords: siem コネクタ、siem、コネクタ、セキュリティ情報、イベントを有効にする
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 00b7a7abbf6c9fcb9395723e5e62ef0e89b2114a
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470529"
---
# <a name="enable-microsoft-defender-for-iot-integration"></a>Microsoft Defender for IoT 統合を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

Microsoft Defender for Endpointが Microsoft Defender for IoT と統合できるようになりました。 この統合により、Microsoft Defender for IoT によって提供されるエージェントレス監視機能を使用して、デバイス検出機能が拡張されます。 これにより、Voice over Internet Protocol (VoIP) デバイス、プリンター、カメラなど、IT ネットワークに接続されたエンタープライズ IoT デバイスのセキュリティ保護に役立ちます。 これにより、組織は、すべての IoT と運用テクノロジ (OT) インフラストラクチャをセキュリティで保護する 1 つの統合ソリューションを利用できます。 詳細については、「[Enterprise IoT ネットワーク保護](/azure/defender-for-iot/organizations/overview-eiot)」を参照してください。

この統合を有効にすると、Microsoft Defender for Endpointネットワーク内の IoT デバイスの特定、識別、セキュリティ保護に役立つ可視性が向上します。 Microsoft Defender for IoT によって検出された IoT デバイス、またはMicrosoft Defender for Endpointは両方のポータルで自動的に同期されます。 これにより、IT デバイスの残りの部分 (ワークステーション、サーバー、モバイル) と共に、完全な OT/IoT インベントリの 1 つの統合ビューが提供されます。

Microsoft Defender for IoT には、追加のデータ ソースを提供するデプロイ可能なネットワーク センサーも含まれています。 統合の一環としてネットワーク センサーを設定すると、IoT デバイスと OT デバイスの最も完全なビューが提供されます。特に、Microsoft Defender for Endpoint センサーが存在しないネットワーク セグメントや、従業員がリモートで情報にアクセスしている場合などです。

## <a name="prerequisites"></a>前提条件

Microsoft Defender for IoT を有効にするには、ユーザーに次のロールが必要です。

- Azure Active Directoryのテナント グローバル管理者
- Microsoft Defender for IoT 統合に使用される Azure サブスクリプションのセキュリティ管理者

## <a name="enabling-the-microsoft-defender-for-iot-integration"></a>Microsoft Defender for IoT 統合の有効化

1. ポータルの [https://security.microsoft.com](https://security.microsoft.com/)ナビゲーション ウィンドウで、**設定** \> **デバイス検出** \> **Microsoft Defender for IoT** を選択します。

   :::image type="content" source="images/enable-defender-for-iot.png" alt-text="IoT 統合のセットアップ" lightbox="images/enable-defender-for-iot.png":::

2. **Azure Active Directory** テナントで使用可能なサブスクリプションのドロップダウン リストから Azure サブスクリプションを選択し、[保存] を選択 **します**。

## <a name="set-up-a-network-sensor"></a>ネットワーク センサーを設定する

Azure サブスクリプションを選択すると、ネットワーク センサーを追加できます。

ネットワーク センサーを追加するには、[ **ネットワーク センサーのセットアップ** ] で **Microsoft Defender for IoT** リンクを選択します。 これにより、Azure portalのオンボード センサーのセットアップ プロセスが表示されます。 詳細については、[Azure portalの Defender for IoT を使用したセンサーの管理に関するページを参照](/azure/defender-for-iot/organizations/how-to-manage-sensors-on-the-cloud)してください。

## <a name="turn-off-subscription-integration"></a>サブスクリプション統合を無効にする

Azure サブスクリプションの統合は、ポータルの Microsoft Defender for IoT 設定ページから [https://security.microsoft.com](https://security.microsoft.com/) 無効にすることができます。 サブスクリプションをオフにすると、Microsoft Defender for IoT によって検出された IoT デバイスがMicrosoft Defender for Endpointデバイス インベントリに表示されなくなります。

## <a name="see-also"></a>関連項目

- [デバイス検出の概要](configure-device-discovery.md)
- [デバイス検出に関する FAQ](device-discovery-faq.md)
