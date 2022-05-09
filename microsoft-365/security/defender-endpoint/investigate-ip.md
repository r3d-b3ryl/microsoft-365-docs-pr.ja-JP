---
title: アラートに関連付けられている IP アドレスを調査する
description: 調査オプションを使用して、デバイスと外部 IP アドレス間の通信の可能性を調べます。
keywords: 調査、調査、IP アドレス、アラート、Microsoft Defender for Endpoint、外部 IP
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: b20a8d5f1f33ebe62fa1ec9a5e8c8e05dbddbc2b
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323347"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

デバイスと外部インターネット プロトコル (IP) アドレス間の通信の可能性を調べます。

Command and Control (C2) サーバーなど、疑わしいまたは既知の悪意のある IP アドレスと通信した組織内のすべてのデバイスを特定すると、侵害、関連ファイル、感染したデバイスの潜在的な範囲を特定するのに役立ちます。

IP アドレス ビューでは、次のセクションから情報を確認できます。

- 世界中の IP
- 逆引き DNS 名
- この IP に関連するアラート
- 組織内の IP
- 有 病 率

## <a name="ip-worldwide-and-reverse-dns-names"></a>IP Worldwide および Reverse DNS 名

[IP アドレスの詳細] セクションには、ASN や逆引き DNS 名などの IP アドレスの属性が表示されます。

## <a name="alerts-related-to-this-ip"></a>この IP に関連するアラート

**この IP に関連するアラート** セクションには、IP に関連付けられているアラートの一覧が表示されます。

## <a name="ip-in-organization"></a>組織内の IP

**[組織内の IP]** セクションには、組織内の IP アドレスの普及率に関する詳細が示されています。

## <a name="prevalence"></a>有 病 率

**[有病率]** セクションには、この IP アドレスに接続されているデバイスの数と、IP が最初に表示され、最後に表示された日時が表示されます。 このセクションの結果は、期間でフィルター処理できます。既定の期間は 30 日です。

## <a name="most-recent-observed-devices-with-ip"></a>IP を使用して観察された最新のデバイス

[IP を含む **最新の監視デバイス** ] セクションでは、IP アドレスで観察されたイベントと関連するアラートを時系列で表示します。

**外部 IP を調査します。**

1. **[検索] バー** のドロップダウン メニューから **[IP**] を選択します。
2. **[検索**] フィールドに IP アドレスを入力します。
3. 検索アイコンをクリックするか、 **Enter** キーを押します。

IP アドレスに関する詳細が表示されます。たとえば、登録の詳細 (使用可能な場合)、逆 IP (ドメインなど)、この IP アドレスと通信した組織内のデバイスの普及 (選択可能な期間中)、この IP アドレスとの通信が観察された組織内のデバイスなどです。

> [!NOTE]
> 検索結果は、組織内のデバイスとの通信で観察された IP アドレスに対してのみ返されます。

検索フィルターを使用して検索条件を定義します。 また、タイムライン検索ボックスを使用して、組織内のすべてのデバイスの表示結果をフィルター処理して、IP アドレス、通信に関連付けられているファイル、および観察された最後の日付との通信を観察することもできます。

デバイス名のいずれかをクリックすると、そのデバイスのビューに移動し、報告されたアラート、動作、およびイベントを引き続き調査できます。

## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpoint アラート キューを表示して整理する](alerts-queue.md)
- [Microsoft Defender for Endpointアラートを管理する](manage-alerts.md)
- [Microsoft Defender for Endpointアラートを調査する](investigate-alerts.md)
- [Microsoft Defender for Endpointアラートに関連付けられているファイルを調査する](investigate-files.md)
- [Microsoft Defender for Endpoint デバイスの一覧のデバイスを調査する](investigate-machines.md)
- [Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する](investigate-domain.md)
- [Microsoft Defender for Endpointでユーザー アカウントを調査する](investigate-user.md)
