---
title: Microsoft 365 ネットワーク評価 (プレビュー)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 ネットワーク評価 (プレビュー)
ms.openlocfilehash: 15eb514980bb53bd32380e44b6bfa174670f6b85
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948318"
---
# <a name="microsoft-365-network-assessment-preview"></a>Microsoft 365 ネットワーク評価 (プレビュー)

Microsoft 365 管理センターの Microsoft 365 ページへの接続において、 **ネットワーク評価** は、多くのネットワークパフォーマンス指標の集計を、0-100 からのポイント値で表された、エンタープライズネットワーク境界の状態のスナップショットに変換します。 ネットワーク評価は、テナント全体と、ユーザーがテナントに接続する各地理的位置の両方に適用されます。 Microsoft 365 管理者は、企業のネットワーク正常性の gestalt をすばやく把握して、グローバルなオフィスの場所についての詳細レポートにすばやくドリルダウンすることが簡単にできます。

ネットワーク評価ポイントの値は、表示時に有効になっている TCP の待機時間、ダウンロード速度、および UDP 接続品質指標の平均測定値です。 Microsoft が所有するネットワークのパフォーマンス指標は、これらの測定値から除外され、評価結果が明確になり、企業ネットワークに固有のものであることを確認できます。

![ネットワーク評価の値](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

非常に低いネットワーク評価の値は、Microsoft 365 クライアントがテナントに接続したり、応答性の高いユーザー操作を維持したりする際に重大な問題が発生することを示唆していますが、高価値は、継続的なパフォーマンスの問題があることを示しています。 80% の値は、ネットワークパフォーマンスによって Microsoft 365 接続または応答性に関して通常のユーザーからの苦情を受けないようにする必要がある正常な基準を表します。 ネットワーク接続の反復的な改善が行われると、この値はユーザーの操作に合わせて増加します。

>[!IMPORTANT]
>Network insights、Microsoft 365 Admin Center でのパフォーマンスに関する推奨事項と評価は現在プレビュー状態であり、機能プレビュープログラムに登録されている Microsoft 365 テナントに対してのみ使用できます。

## <a name="network-assessment-panel"></a>ネットワーク評価パネル

テナントまたは特定のオフィスの場所にスコープが設定されているかどうかにかかわらず、各ネットワーク評価には、評価に関する詳細情報がパネルに表示されます。 このパネルには、評価の棒グラフがパーセンテージとして表示されます。また、測定データを受け取ったワークロードのみを含む各コンポーネントワークロードの合計ポイントとして評価されます。 オフィスの場所のネットワーク評価では、office の場所と同じ都市にデータを報告したすべての Microsoft 365 クライアントの中央にあるベンチマークも示しています。

![ネットワーク評価の値の例](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

パネルの [ **評価] ブレークダウン** には、各コンポーネントのワークロードの評価が表示されます。

**評価履歴**には、過去30日間の評価とベンチマークが表示されます。 [履歴] タブを使用して、任意のオフィスの場所の測定基準履歴を最大2年間報告することもできます。

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>テナントのネットワーク評価とオフィスの場所ネットワークの評価

ネットワーク評価は、Microsoft のネットワークへのオフィスの場所のネットワーク境界の設計を測定します。 ネットワーク境界の改善は、各オフィスの場所で行うことをお勧めします。または、ネットワーク接続が集約されている場合は、複数の場所に影響を与える改良が行われることがあります。

ネットワークパフォーマンスの概要ページにある Microsoft 365 テナント全体のネットワーク評価の値と、その場所の要約ページにある検出された各オフィスの場所の特定の値を示します。

## <a name="exchange-online"></a>Exchange Online

Exchange Online の場合、クライアントマシンから Exchange フロントエンドサーバーへの TCP 遅延が測定されます。 これは、ネットワークが顧客の LAN および WAN を通過する距離の影響を受ける可能性があります。 また、ネットワークの仲介装置やサービスによって影響を受けたり、接続が遅延したり、パケットが再送信されたりする可能性もあります。 前の3日間のすべての測定値に対して、median (50 パー百分位または P50 メジャーとも呼ばれる) が使用されます。

Exchange Online の評価は、次の表を使用して行われます。 しきい値間の TCP 遅延時間は、バンド内で直線的に割り当てられます。

| TCP 遅延   | Points |
| :------------ | :----- |
| 10ms 以下  | 100    |
| 25ms          | 80     |
| 100ミリ秒         | 60     |
| 200ms         | 40     |
| 300ms 秒         | 1280     |
| 350ms 以上 | .0      |

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online では、ユーザーが SharePoint Online または OneDrive からドキュメントにアクセスするために使用できるダウンロード速度が測定されます。 このことは、クライアントコンピューターと Microsoft のネットワーク間のネットワーク回線で利用可能な帯域幅の影響を受ける可能性があります。 また、複雑なネットワークデバイスや、混雑している Wi-fi エリアでボトルネックに存在するネットワーク輻輳による影響を受けることもあります。 ダウンロード速度は、1秒あたりのメガバイト (メガビット/秒) の約1秒単位で計測されます。 25分位 (P25 メジャーとも呼ばれる) は、前の3日間のすべての測定値に対して使用されます。

SharePoint Online の評価は、次の表を使用して行われます。 しきい値間のダウンロード速度の数値には、バンド内で直線的にポイントが割り当てられます。

| ダウンロード速度 | Points |
| :------------- | :----- |
| 20MBps 以上 | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 1280     |
| 0MBps          | .0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Microsoft Teams では、ネットワーク品質は UDP 遅延、UDP ジッタ、および UDP パケット損失として測定されます。 UDP は、Microsoft Teams の通話と電話会議の音声およびビデオメディア接続に使用されます。 これは、より一般的な TCP プロトコルに対して UDP が個別に構成されているため、ネットワークの UDP サポートの接続のギャップに加えて、遅延とダウンロードの速度の場合と同じ要因によって影響を受ける可能性があります。 前の3日間のすべての測定値に対して、median (50 パー百分位または P50 メジャーとも呼ばれる) が使用されます。 

Microsoft Teams の評価は、次の表を使用して行います。 表示されているポイントを実現するには、3つの UDP 測定値をしきい値より上にする必要があります。 バンド内の1つの場所に対する評価はありません。

| UDP パケット損失 | UDP 遅延 | UDP ジッタ | Points |
| :-------------- | :---------- | :--------- | :----- |
| 0.25%           | 60ms 秒        | 15ms 秒       | 100    |
| 1.00%           | 120ミリ秒       | 40ms 秒       | 80     |
| 1.50%           | 240ms 秒       | 65ms       | 60     |
| 3.00%           | 275ms 秒       | 80ms 秒       | 40     |
| 5.00%           | 350ms       | 150ms 秒      | 1280     |
| 高      | 高  | 高 | .0      |

## <a name="related-topics"></a>関連項目

[Microsoft 365 管理センター (プレビュー) でのネットワークパフォーマンスに関する推奨事項](office-365-network-mac-perf-overview.md)

[Microsoft 365 network performance insights (プレビュー)](office-365-network-mac-perf-insights.md)

[M365 管理センターでの Microsoft 365 の接続テスト (プレビュー)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 ネットワーク接続ロケーションサービス (プレビュー)](office-365-network-mac-location-services.md)
