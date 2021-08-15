---
title: アラートに関連付けられた IP アドレスを調査する
description: 調査オプションを使用して、デバイスと外部 IP アドレス間の通信の可能性を調べる。
keywords: 調査、調査、IP アドレス、アラート、Microsoft Defender for Endpoint、外部 IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: bd0d9dda9edeb27a472474f071cf67ff1463f23b4c82577b9c902b1ec84eecce
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53839593"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

デバイスと外部インターネット プロトコル (IP) アドレス間の通信の可能性を調べる。

Command and Control (C2) サーバーなど、疑わしいまたは既知の悪意のある IP アドレスと通信した組織内のすべてのデバイスを識別すると、侵害、関連ファイル、感染したデバイスの潜在的な範囲を特定するのに役立ちます。

IP アドレス ビューでは、次のセクションから情報を確認できます。

- 世界中の IP
- DNS 名の逆引き
- この IP に関連するアラート
- 組織内の IP
- 有病率

## <a name="ip-worldwide-and-reverse-dns-names"></a>IP Worldwide および Reverse DNS 名

[IP アドレスの詳細] セクションには、その ASN やリバース DNS 名などの IP アドレスの属性が表示されます。

## <a name="alerts-related-to-this-ip"></a>この IP に関連するアラート

[ **この IP に関連するアラート** ] セクションには、IP に関連付けられているアラートの一覧が表示されます。

## <a name="ip-in-organization"></a>組織内の IP

[ **組織内の IP]** セクションには、組織内の IP アドレスの普及率に関する詳細が表示されます。

## <a name="prevalence"></a>有病率

[ **有病率** ] セクションには、この IP アドレスに接続したデバイスの数と、IP が最初と最後に表示された時点が表示されます。 このセクションの結果は、期間別にフィルター処理できます。既定の期間は 30 日です。

## <a name="most-recent-observed-devices-with-ip"></a>IP を含む最新の観測デバイス

[IP **を含む最新** の観測デバイス] セクションには、IP アドレスで観測されたイベントと関連するアラートに関する時系列ビューが表示されます。

**外部 IP を調査します。**

1. [検索] バーの **ドロップダウン メニューから** **[IP]** を選択します。
2. [検索] フィールドに IP アドレス **を入力** します。
3. 検索アイコンをクリックするか、Enter キーを **押します**。

IP アドレスの詳細は、登録の詳細 (利用可能な場合)、リバース IP (ドメインなど)、この IP アドレスと通信した組織内のデバイスの普及率 (選択可能な期間中)、およびこの IP アドレスとの通信が観察された組織内のデバイスなど、表示されます。

> [!NOTE]
> 検索結果は、組織内のデバイスとの通信で観察された IP アドレスに対してのみ返されます。

検索条件を定義するには、検索フィルターを使用します。 タイムライン検索ボックスを使用して、IP アドレス、通信に関連付けられたファイル、および最後に観測された日付と通信している組織内のすべてのデバイスの表示結果をフィルター処理することもできます。

デバイス名をクリックすると、そのデバイスのビューにアクセスし、報告されたアラート、動作、およびイベントを引き続き調査できます。

## <a name="related-topics"></a>関連トピック

- [Microsoft Defender for Endpoint アラート キューを表示して整理する](alerts-queue.md)
- [エンドポイント通知の Microsoft Defender の管理](manage-alerts.md)
- [Microsoft Defender for Endpoint アラートの調査](investigate-alerts.md)
- [Microsoft Defender for Endpoint アラートに関連付けられたファイルを調査する](investigate-files.md)
- [Microsoft Defender for Endpoint Devices リストのデバイスを調査する](investigate-machines.md)
- [Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する](investigate-domain.md)
- [Microsoft Defender for Endpoint のユーザー アカウントを調査する](investigate-user.md)
