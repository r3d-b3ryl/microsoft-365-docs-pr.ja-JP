---
title: Microsoft Defender for Endpoint ドメインを調査する
description: 調査オプションを使用して、デバイスとサーバーが悪意のあるドメインと通信しているかどうかを確認します。
keywords: ドメイン、ドメイン、悪意のあるドメイン、Microsoft Defender for Endpoint、アラート、URL を調査する
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: bc309c3215524b20ff93c6f1f9c16248fdfffac1
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/29/2021
ms.locfileid: "61218624"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatedomain-abovefoldlink)

ドメインを調査して、エンタープライズ ネットワーク内のデバイスとサーバーが既知の悪意のあるドメインと通信しているかどうかを確認します。

検索機能を使用するか、 **デバイス タイムライン** からドメイン リンクをクリックして、ドメインを調査できます。

URL ビューでは、次のセクションから情報を確認できます。

- URL の詳細、連絡先、ネームサーバー
- この URL に関連するアラート 
- 組織内の URL
- URL を含む最新の監視デバイス

## <a name="url-worldwide"></a>世界中の URL

**[URL Worldwide]** セクションには、URL、Whois の詳細へのリンク、関連するオープン インシデントの数、アクティブなアラートの数が一覧表示されます。

## <a name="incident"></a>インシデント

**インシデント** カードには、過去 180 日間のインシデントのすべてのアクティブなアラートの横棒グラフが表示されます。

## <a name="prevalence"></a>有 病 率

**有病率** カードは、組織内の URL の一定期間にわたる有病率に関する詳細を提供します。

既定の期間は過去 30 日間ですが、カードの隅にある下向き矢印を選択して範囲をカスタマイズできます。 使用可能な最短範囲は過去 1 日の有病率ですが、最長範囲は過去 6 か月間です。

## <a name="alerts"></a>アラート

[ **アラート]** タブには、URL に関連付けられているアラートの一覧が表示されます。 次の表は、アラート キュー画面に表示されるアラートのフィルター処理されたバージョンで、ドメインに関連付けられているアラート、重大度、状態、関連するインシデント、分類、調査の状態などを示しています。

[アラート] タブは、列ヘッダーの上にあるアクション メニューから **[列のカスタマイズ** ] を選択することで、多かれ少なかれ情報を表示するように調整できます。 表示される項目の数は、同じメニューの **ページごとに項目** を選択することで調整することもできます。

## <a name="observed-in-organization"></a>組織内で観察される

[ **組織の監視]** タブには、URL で観察されたイベントと関連するアラートに関する時系列ビューが表示されます。 このタブには、タイムラインと、時刻、デバイス、発生した内容の簡単な説明など、イベントの詳細を一覧表示するカスタマイズ可能なテーブルが含まれます。 

テーブル ヘッダーの上のテキスト フィールドに日付を入力すると、さまざまな期間のイベントを表示できます。 タイムラインのさまざまな領域を選択して、時間範囲をカスタマイズすることもできます。

**ドメインを調査する:**

1. **[検索] バー** のドロップダウン メニューから **[URL] を** 選択します。
2. **[検索**] フィールドに URL を入力します。
3. 検索アイコンをクリックするか、 **Enter** キーを押します。 URL に関する詳細が表示されます。 注: 検索結果は、組織内のデバイスからの通信で観察される URL に対してのみ返されます。
4. 検索フィルターを使用して検索条件を定義します。 また、タイムライン検索ボックスを使用して、組織内のすべてのデバイスの表示結果をフィルター処理して、URL、通信に関連付けられているファイル、および観察された最後の日付を確認することもできます。
5. デバイス名のいずれかをクリックすると、そのデバイスのビューに移動し、報告されたアラート、動作、およびイベントを引き続き調査できます。

## <a name="related-topics"></a>関連項目
- [Microsoft Defender for Endpoint アラート キューを表示して整理する](alerts-queue.md)
- [Microsoft Defender for Endpointアラートを管理する](manage-alerts.md)
- [Microsoft Defender for Endpointアラートを調査する](investigate-alerts.md)
- [Microsoft Defender for Endpointアラートに関連付けられているファイルを調査する](investigate-files.md)
- [Microsoft Defender for Endpoint デバイスの一覧のデバイスを調査する](investigate-machines.md)
- [Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する](investigate-ip.md)
- [Microsoft Defender for Endpointでユーザー アカウントを調査する](investigate-user.md)
