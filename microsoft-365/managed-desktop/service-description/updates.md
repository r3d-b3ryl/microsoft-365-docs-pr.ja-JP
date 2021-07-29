---
title: 更新プログラムの処理方法は、Microsoft マネージド デスクトップ
description: 最新Microsoft マネージド デスクトップ保つことは、速度と安定性のバランスです。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f817831cda584dc1aa6c968d7332939c68f48e8b
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53622270"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>更新プログラムの処理方法は、Microsoft マネージド デスクトップ


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft マネージド デスクトップ、すべてのデバイスを最新のクラウドベースのインフラストラクチャに接続します。 アプリケーションWindows、Office、ファームウェア、およびビジネス向け Microsoft Storeアプリケーションを最新の状態に保つことは、速度と安定性のバランスです。 更新グループを使用して、オペレーティング システムの更新プログラムとポリシーが安全に展開されます。 詳細については、「変更およびリリース プロセス」[のMicrosoft マネージド デスクトップを参照してください](https://www.microsoft.com/videoplayer/embed/RE4mWqP)。 

Microsoft がリリースした更新プログラムは累積的であり、品質または機能の更新プログラムとして分類されます。
詳細については、「ビジネス向け更新[Windows更新プログラムの種類」を参照してください](/windows/deployment/update/waas-manage-updates-wufb#update-types)。 

## <a name="update-groups"></a>グループを更新する


Microsoft マネージド デスクトップ 4 つの Azure ADを使用して更新プログラムを管理します。

- **テスト**: Azure Microsoft マネージド デスクトップ組織 ("tenant") にプッシュされたポリシーの変更、オペレーティング システムの更新、機能の更新、その他の変更AD検証するために使用されます。 テストまたは早期フィードバックを提供できるユーザーに最適です。 テスト グループは、確立されたサービス レベル契約およびユーザー サポートから除外されます。 このグループは、アプリケーションと新しいポリシーまたはオペレーティング システムの変更との互換性を検証するために使用できます。  
- **最初**: リリース前の更新プログラムの対象となる可能性がある初期のソフトウェア導入者とデバイスが含まれています。 テスト リングでテスト中にカバーされていないシナリオがある場合、このグループ内のデバイスで停止が発生する可能性があります。
- **Fast**: 安定性よりも速度を優先します。 Broad グループに提供される前に品質の問題を検出する場合に役立ちます。 このグループは、検証の次の層として機能しますが、通常は Test グループと First グループよりも安定しています。 
- **Broad**: 機能と品質の更新プログラムを利用できる最後のグループ。 このグループには、Azure ADのほとんどのユーザーが含まれているため、展開の速度に対する安定性が優れています。 アプリのテストは、環境が最も安定しており、ここで行う必要があります。

### <a name="moving-devices-between-update-groups"></a>更新グループ間でのデバイスの移動
一部のデバイスで最後に更新プログラムを受信し、その他のデバイスで最初に更新プログラムを受け取る必要がある場合があります。 これらのデバイスを適切な更新グループに移動するには、「展開グループにデバイスを割り当 [てる」を参照してください](../working-with-managed-desktop/assign-deployment-group.md)。

これらの展開グループ内の役割と責任の詳細については、「役割と[Microsoft マネージド デスクトップ」を参照してください。](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>更新Microsoft マネージド デスクトップの使用 
管理するサービスには、アプリの展開など、すべての管理対象デバイスをターゲットに設定する必要がある部分があります。

## <a name="how-update-deployment-works"></a>更新プログラムの展開のしくみ:
1. Microsoft マネージド デスクトップ表で指定したスケジュールに従って、新しい機能または品質更新プログラムを展開します。
2. 展開中、Microsoft マネージド デスクトップ診断データとユーザー サポート システムに基づいて障害や中断の兆候を監視します。 検出された場合は、現在および将来のすべてのグループへの展開を直ちに一時停止します。
    - 例: 品質更新プログラムを最初のグループに展開している間に問題が検出された場合、展開を First、Fast、および Broad に更新すると、問題が軽減されるまですべて一時停止されます。
    - 互換性の問題を報告するには、管理者ポータルでチケットをMicrosoft マネージド デスクトップできます。
    - 機能と品質の更新プログラムは個別に一時停止されます。 一時停止は既定で 35 日間有効ですが、問題が軽減されるかどうかに応じて縮小または拡張できます。
3. グループが一時停止解除されると、表のスケジュールに従って展開が再開されます。
4. ユーザーは、一定の期間 (期限と呼ばれる、更新プログラムがデバイスに提供された時間から測定される) の再起動通知に応答できます。その間、デバイスはアクティブな時間外にのみ自動的に再起動します。 この期間が経過すると、期限に達し、アクティブな時間に関係なく、次に利用可能な機会にデバイスが再起動します。 品質更新プログラムの期限は 3 日間です。機能更新プログラムの場合は 5 日間です。

この展開プロセスは、機能更新プログラムと品質更新プログラムの両方に適用されます。タイムラインはそれぞれ異なります。


<table>
    <tr><th colspan="5">展開設定の更新</th></tr>
    <tr><th>更新プログラムの種類</th><th>テスト</th><th>第 1</th><th>高速</th><th>広範な質問</th></tr>
    <tr><td>オペレーティング システムの品質更新プログラム</td><td>0 日</td><td>0 日</td><td>0 日</td><td>7 日間</td></tr>
    <tr><td>オペレーティング システムの機能更新プログラム</td><td>0 日</td><td>30 日間</td><td>60 日</td><td>90 日間</td></tr>
    <tr><td>ドライバー/ファームウェア</td><td colspan="4">品質更新プログラムのスケジュールに従う</td></tr>
    <tr><td>ウイルス対策の定義</td><td colspan="4">各スキャンで更新</td></tr>
    <tr><td>Microsoft 365 Apps for Enterprise</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">詳細情報</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">詳細情報</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/teams#updates">詳細情報</a></td></tr>
</table>

>[!NOTE]
>これらの延期期間は、すべてのユーザーに対して高いセキュリティとパフォーマンス基準を確保するように意図的に設計されています。 さらに、Microsoft マネージド デスクトップ デバイス全体で収集されたデータと、更新プログラムの範囲と影響の変化に基づいて、Microsoft マネージド デスクトップ は、任意の展開グループおよびすべての展開グループの上記の延期期間の長さをアドホックに変更する柔軟性を備えています。
>
>Microsoft マネージド デスクトップ各機能リリースの独立した評価をWindows、管理テナントに対する必要性と有用性を評価します。 したがって、すべてのMicrosoft マネージド デスクトップ更新プログラムを展開する場合と展開Windows可能性があります。 

## <a name="windows-insider-program"></a>Windows Insider Program

Microsoft マネージド デスクトップ Insider プログラムの一部であるデバイスWindowsサポートされていません。 このWindows Insider プログラムは、ソフトウェアのプレリリースWindows検証するために使用され、ミッション クリティカルではないデバイスを対象とします。 重要な Microsoft イニシアチブですが、実稼働環境での広範な展開を目的としません。 

Insider ビルドに含Windowsデバイスはテスト グループに組み込む可能性があります。更新サービス レベル契約とユーザー サポートは、Microsoft マネージド デスクトップ から除外されます。

## <a name="bandwidth-management"></a>帯域幅管理

すべてのオペレーティング [システムとドライバーの](/windows/deployment/update/waas-delivery-optimization) 更新プログラムに配信の最適化を使用します。 配信の最適化では、企業ネットワーク内のピアから更新プログラムをWindowsして、Windows Update サービスからのダウンロード サイズを最小限に抑える。
