---
title: Microsoft Managed Desktop での更新プログラムの処理方法
description: Microsoft Managed Desktop を最新の状態に保つことは、速度と安定性のバランスです。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: bf6ead692a82d485f6a8e3b3148bc05484c887a8
ms.sourcegitcommit: 9f0e84835121ce6228fdc69182c24be7ad1cb20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2022
ms.locfileid: "62896017"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop での更新プログラムの処理方法

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop は、すべてのデバイスを最新のクラウドベースのインフラストラクチャに接続します。

アプリケーションWindows、Office、ファームウェア、およびビジネス向け Microsoft Storeアプリケーションを最新の状態に保つことは、速度と安定性のバランスです。 更新グループを使用して、オペレーティング システムの更新プログラムとポリシーが安全に展開されます。 詳細については、「 [Microsoft Managed Desktop Change and Release Process」のビデオを参照してください](https://www.microsoft.com/videoplayer/embed/RE4mWqP)。

Microsoft がリリースした更新プログラムは累積的であり、品質または機能の更新プログラムとして分類されます。 詳細については、「ビジネス向[け更新Windows更新プログラムの種類」を参照してください](/windows/deployment/update/waas-manage-updates-wufb#update-types)。

## <a name="update-groups"></a>グループを更新する

Microsoft Managed Desktop では、4 つのAzure ADグループを使用して更新プログラムを管理します。

| Group | 説明 |
| ------ | ------ |
| テスト | Microsoft Managed Desktop ポリシーの変更、オペレーティング システムの更新プログラム、機能更新プログラム、および組織 ("tenant") にプッシュされたその他Azure AD検証するために使用されます。 テスト グループは次の場合です。 <br><ul><li>テストまたは早期フィードバックを提供できるユーザーに最適です。</li><li>確立されたサービス レベル契約およびユーザー サポートから除外されます。</li><li>新しいポリシーまたはオペレーティング システムの変更とアプリケーションの互換性を検証するために使用できます。</li></ul> |
| 第 1 | リリース前の更新プログラムの対象となる可能性がある初期のソフトウェア導入者とデバイスが含まれています。 <br><br> テストリングでテスト中にカバーされなかったシナリオがある場合、このグループのデバイスで停止が発生する可能性があります。 |
| 高速 | 安定性よりも速度を優先します。 Fast グループは次の場合です。 <br><ul><li>Broad グループに提供される前に品質の問題を検出する場合に役立ちます。</li> <li>検証の次の層で、通常は Test グループと First グループよりも安定しています。</li></ul> |
| 広範な質問 | このグループは、機能と品質の更新プログラムを利用できる最後のグループです。 <br><br> Broad グループには、組織のほとんどのユーザー Azure AD含まれているため、展開の速度に対する安定性が優れています。 アプリのテストは、環境が最も安定性が高いので、このグループで行う必要があります。 |

### <a name="moving-devices-between-update-groups"></a>更新グループ間でのデバイスの移動

一部のデバイスで最後に更新プログラムを受信し、その他のデバイスで最初に更新プログラムを受け取る必要がある場合があります。 これらのデバイスを適切な更新グループに移動するには、「デバイスを展開グループに割り当てる [」を参照してください](../working-with-managed-desktop/assign-deployment-group.md)。

これらの展開グループ内の役割と責任の詳細については、「 [Microsoft Managed Desktop Roles and responsibilits」を参照してください。](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>Microsoft Managed Desktop 更新グループの使用

管理するサービスには、アプリの展開など、すべての管理対象デバイスをターゲットに設定する必要がある部分があります。

## <a name="update-deployment"></a>展開の更新

以下では、更新プログラムの展開のしくみについて説明します。

| 手順 | 説明 |
| ------ | ------ |
| 手順 1 | Microsoft Managed Desktop は、次の表に示すスケジュールに従って新しい機能または品質更新プログラムを展開します。|
| 手順 2 | 展開中、Microsoft Managed Desktop は、診断データとユーザー サポート システムに基づいて、障害の兆候や中断を監視します。 検出された場合は、現在および将来のすべてのグループへの展開を直ちに一時停止します。<br><br> たとえば、品質更新プログラムを最初のグループに展開している間に問題が検出された場合、展開を First、Fast、および Broad グループに更新すると、問題が軽減されるまで一時停止されます。 <br><br> 互換性の問題を報告するには、Microsoft Managed Desktop Admin ポータルでチケットを提出します。 <br><br> 機能と品質の更新プログラムは個別に一時停止されます。 一時停止は既定で 35 日間有効です。 ただし、問題が軽減されるかどうかに応じて、縮小または拡張できます。 |
| 手順 3 | グループが一時停止解除されると、表のスケジュールに従って展開が再開されます。 |
| 手順 4| ユーザーは、一定の期間、再起動通知に応答できます。 この期間は期限と呼び、更新プログラムがデバイスに提供された時点から測定されます。 <br><br> この間、デバイスはアクティブな時間外にのみ自動的に再起動します。 この期間が経過すると、期限に達し、アクティブな時間に関係なく、次に利用可能な機会にデバイスが再起動します。 <br><br> 品質更新プログラムの期限は 3 日間です。機能更新プログラムの場合は、5 日間です。 |

> [!NOTE]
> この展開プロセスは、機能更新プログラムと品質更新プログラムの両方に適用されます。タイムラインはそれぞれ異なります。

## <a name="deployment-settings"></a>展開設定

以下に示す展開設定を更新します。

| 更新プログラムの種類 | テスト | 第 1 | 高速 | 広範な質問 |
| ------ | ------ | ------ | ------ | ------ |
| オペレーティング システムの品質更新プログラム | ゼロ日 | ゼロ日 | ゼロ日 | 7 日間 |
| オペレーティング システムの機能更新プログラム | ゼロ日 | 30 日間 | 60 日 | 90 日間 |
| ドライバー/ファームウェア | 品質更新プログラムのスケジュールに従います。 | 品質更新プログラムのスケジュールに従います。 | 品質更新プログラムのスケジュールに従います。 | 品質更新プログラムのスケジュールに従います。 |
| ウイルス対策の定義 | スキャンごとに更新されます。 | スキャンごとに更新されます。 | スキャンごとに更新されます。 | スキャンごとに更新されます。 |
| Microsoft 365 Apps for Enterprise | [詳細情報](../get-started/m365-apps.md#updates-to-microsoft-365-apps) | [詳細情報](../get-started/m365-apps.md#updates-to-microsoft-365-apps) | [詳細情報](../get-started/m365-apps.md#updates-to-microsoft-365-apps) | [詳細情報](../get-started/m365-apps.md#updates-to-microsoft-365-apps) |
| Microsoft Edge | [詳細情報](../get-started/edge-browser-app.md#updates-to-microsoft-edge) | [詳細情報](../get-started/edge-browser-app.md#updates-to-microsoft-edge) | [詳細情報](../get-started/edge-browser-app.md#updates-to-microsoft-edge) | [詳細情報](../get-started/edge-browser-app.md#updates-to-microsoft-edge) |
| Microsoft Teams | [詳細情報](../get-started/teams.md#updates) | [詳細情報](../get-started/teams.md#updates) | [詳細情報](../get-started/teams.md#updates) | [詳細情報](../get-started/teams.md#updates) |

>[!NOTE]
>これらの延期期間は、すべてのユーザーに対して高いセキュリティとパフォーマンス基準を確保するように意図的に設計されています。<br><br> Microsoft Managed Desktop のすべてのデバイスで収集されたデータと、更新プログラムの範囲と影響の変化に基づいて、Microsoft Managed Desktop は、任意の展開グループおよびすべての展開グループの上記の延期期間の長さをアドホックに変更する柔軟性を備えています。
>
>Microsoft Managed Desktop では、管理テナントの必要性とWindowsを評価するために、各機能リリースの独立した評価を実施します。 したがって、Microsoft Managed Desktop は、すべての機能更新プログラムを展開Windows可能性があります。

## <a name="windows-insider-program"></a>Windows Insider Program

Microsoft Managed Desktop は、Insider プログラムの一部であるデバイスWindowsサポートされていません。

Insider Windowsは、ソフトウェアのプレリリースを検証するためにWindowsされます。 これは、ミッション クリティカルではないデバイスを対象とします。 重要な Microsoft イニシアチブですが、実稼働環境での広範な展開を目的としません。

Insider ビルドに含Windowsデバイスは、テスト グループに追加できます。 これらのデバイスは、Microsoft Managed Desktop の更新サービス レベル契約とユーザー サポートから除外されます。

## <a name="bandwidth-management"></a>帯域幅管理

すべてのオペレーティング [システムとドライバーの](/windows/deployment/update/waas-delivery-optimization) 更新プログラムに配信の最適化を使用します。 配信の最適化では、企業ネットワーク内のピアから更新プログラムをWindowsして、Windows Update サービスからのダウンロード サイズを最小限に抑える。
