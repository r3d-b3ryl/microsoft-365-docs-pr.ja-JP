---
title: Microsoft Defender for Endpoint ドメインの調査
description: 調査オプションを使用して、デバイスとサーバーが悪意のあるドメインと通信しているのを確認します。
keywords: ドメイン、ドメイン、悪意のあるドメイン、Microsoft Defender for Endpoint、アラート、URL を調査する
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
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 98e4c781f28f1a89eb3ba9878b65ef57d0e40ea8
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53619557"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink)

ドメインを調査して、エンタープライズ ネットワーク内のデバイスとサーバーが既知の悪意のあるドメインと通信しているのを確認します。

検索機能を使用するか、デバイス タイムラインからドメイン リンクをクリックして、ドメインを **調査できます**。

URL ビューでは、次のセクションから情報を確認できます。

- URL の詳細、連絡先、ネームサーバー
- この URL に関連するアラート 
- 組織内の URL
- URL を含む最新の観測デバイス

## <a name="url-worldwide"></a>世界中の URL

[URL **Worldwide]** セクションには、URL、Whois の詳細情報へのリンク、関連する開いているインシデントの数、アクティブなアラートの数が一覧表示されます。

## <a name="incident"></a>インシデント

インシデント **カード** には、過去 180 日間のインシデントでアクティブなすべてのアラートの棒グラフが表示されます。

## <a name="prevalence"></a>有病率

[ **有病率** ] カードは、指定した期間に組織内の URL の普及率に関する詳細を提供します。

既定の期間は過去 30 日間ですが、カードの隅にある下向きの矢印を選択して範囲をカスタマイズできます。 利用可能な最短の範囲は、過去 1 日の有病率の範囲ですが、最も長い範囲は過去 6 か月間です。

## <a name="alerts"></a>アラート

[ **アラート]** タブには、URL に関連付けられているアラートの一覧が表示されます。 次に示す表は、[アラート キュー] 画面に表示されるアラートのフィルター処理されたバージョンで、ドメインに関連付けられたアラート、重大度、状態、関連するインシデント、分類、調査状態などにのみ表示されます。

[アラート] タブは、列ヘッダーの上にあるアクション メニューから[列のカスタマイズ] を選択して、多かれ少なかれ情報を表示するために調整できます。 同じメニューでページごとにアイテムを選択することで、表示されるアイテムの **数を調整** することもできます。

## <a name="observed-in-organization"></a>組織内で観察される

[ **組織で観察]** タブには、URL で観察されたイベントと関連付けられたアラートに関する時系列ビューが表示されます。 このタブには、タイムラインと、時間、デバイス、発生した内容の簡単な説明など、イベントの詳細を示すカスタマイズ可能なテーブルが含まれます。 

テーブル ヘッダーの上のテキスト フィールドに日付を入力すると、異なる期間のイベントを表示できます。 タイムラインの異なる領域を選択して、時間範囲をカスタマイズすることもできます。

**ドメインを調査します。**

1. [検索] バーの **ドロップダウン メニューから** **[URL]** を選択します。
2. [検索] フィールドに URL **を入力** します。
3. 検索アイコンをクリックするか、Enter キーを **押します**。 URL の詳細が表示されます。 注: 検索結果は、組織内のデバイスからの通信で観察された URL に対してのみ返されます。
4. 検索条件を定義するには、検索フィルターを使用します。 タイムライン検索ボックスを使用して、URL との通信が観察された組織内のすべてのデバイス、通信に関連付けられたファイル、および観測された最後の日付の表示結果をフィルター処理することもできます。
5. デバイス名をクリックすると、そのデバイスのビューにアクセスし、報告されたアラート、動作、およびイベントを引き続き調査できます。

## <a name="related-topics"></a>関連項目
- [Microsoft Defender for Endpoint アラート キューを表示して整理する](alerts-queue.md)
- [エンドポイント通知の Microsoft Defender の管理](manage-alerts.md)
- [Microsoft Defender for Endpoint アラートの調査](investigate-alerts.md)
- [Microsoft Defender for Endpoint アラートに関連付けられたファイルを調査する](investigate-files.md)
- [Microsoft Defender for Endpoint Devices リストのデバイスを調査する](investigate-machines.md)
- [Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する](investigate-ip.md)
- [Microsoft Defender for Endpoint のユーザー アカウントを調査する](investigate-user.md)
