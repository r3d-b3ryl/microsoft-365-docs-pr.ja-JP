---
title: Microsoft マネージド デスクトップでの更新プログラムの処理方法
description: Microsoft マネージド デスクトップを最新の状態に保つことは、速度と安定性のバランスです。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4d8de363cc9111fade719fdf5384519d1236f431
ms.sourcegitcommit: 05657b39eaafc0503b01c6adcc5d8a5e615dc02c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50031341"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップでの更新プログラムの処理方法


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft マネージド デスクトップは、すべてのデバイスを最新のクラウドベースのインフラストラクチャに接続します。 Windows、Officeドライバー、ファームウェア、およびビジネス向け Microsoft Store アプリケーションを最新の状態に保つことは、速度と安定性のバランスです。 展開グループは、オペレーティング システムの更新プログラムとポリシーを安全な方法で展開するために使用されます。 詳細については、ビデオ「Microsoft マネージド デスクトップの変更とリリース [プロセス」を参照してください](https://www.microsoft.com/videoplayer/embed/RE4mWqP)。

Microsoft によってリリースされた更新プログラムは累積的であり、品質更新プログラムまたは機能更新プログラムとして分類されます。
詳しくは [、「Windows Update for Business: 更新プログラムの種類」をご覧ください](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)。 

## <a name="update-groups"></a>グループを更新する

Microsoft マネージド デスクトップでは、4 つの Azure AD グループを使用して更新プログラムを管理します。

- **テスト**: Microsoft マネージド デスクトップ ポリシーの変更、オペレーティング システムの更新プログラム、機能更新プログラム、テナントにプッシュされたその他の変更を検証するために使用されます。 テスト グループにユーザーを配置する必要があります。 テスト グループは、確立されたサービス レベル契約とユーザー サポートから除外されます。 このグループは、新しいポリシーやオペレーティング システムの変更に対するアプリケーションの互換性を検証するために使用できます。  
- **1 つ** 目: プレリリース版の更新プログラムの対象となる可能性がある初期のソフトウェア導入者とデバイスが含まれています。 テスト リングでのテスト中にカバーされていないシナリオがある場合、このグループ内のデバイスで停止が発生する可能性があります。
- **高速**: 安定性よりも速度を優先します。 広範グループに提供する前に品質の問題を検出する場合に役立ちます。 このグループは検証の次のレイヤーとして機能しますが、通常は Test グループと First グループよりも安定しています。 
- **広範**: 機能更新プログラムと品質更新プログラムを利用できる最後のグループ。 このグループにはテナント内のほとんどのユーザーが含まれているため、展開の速度より安定性が高い。 アプリのテストは、環境が最も安定しており、ここで行う必要があります。 

### <a name="moving-devices-between-update-groups"></a>更新グループ間でのデバイスの移動
一部のデバイスで最後に更新プログラムを受信し、その他の更新プログラムを最初に受け取る必要がある場合があります。 これらのデバイスを適切な更新グループに移動するには[](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/admin-support?view=o365-worldwide)、管理者サポート要求を送信します。デバイスが移行されます。 

> [!NOTE]
> ユーザーを別の更新グループに移動する必要がある場合は、サポート要求を送信します。 更新グループ間でデバイスを自分で移動しない。 デバイスが正しく移動されないと、重大な結果が発生します。 デバイスが予期せず更新され、ポリシーが競合してデバイス構成が変更される可能性があります。

これらの展開グループ内の役割と責任の詳細については、「Microsoft マネージド デスクトップの役割と責任」 [を参照してください。](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>Microsoft マネージド デスクトップ更新グループの使用 
管理するサービスには、アプリの展開など、すべての管理対象デバイスを対象とする必要がある部分があります。 このような場合は、更新グループを使用して、それらのグループのメンバーシップを追加、削除、または変更できないことを理解して、それらのユーザーにアクセスします。 

## <a name="how-update-deployment-works"></a>更新プログラムの展開のしくみ:
1. Microsoft マネージド デスクトップでは、次の表に示すスケジュールに従って、新しい機能更新プログラムまたは品質更新プログラムが展開されます。
2. 展開時に、Microsoft マネージド デスクトップは、診断データとユーザー サポート システムに基づいて障害や中断の兆候を監視します。 検出された場合は、現在および将来のすべてのグループへの展開を直ちに一時停止します。
    - 例: 品質更新プログラムを最初のグループに展開している間に問題が検出された場合、展開を First、Fast、Broad に更新すると、問題が解決されるまですべて一時停止されます。
    - 互換性の問題を報告するには、Microsoft マネージド デスクトップ管理ポータルでチケットを提出します。
    - 機能更新プログラムと品質更新プログラムは個別に一時停止されます。 一時停止は既定で 35 日間有効になりますが、問題が修復されるかどうかに応じて、縮小または延長できます。
3. グループの一時停止が解除されると、表のスケジュールに従って展開が再開されます。

この展開プロセスは機能更新プログラムと品質更新プログラムの両方に適用されます。タイムラインはそれぞれ異なります。




<table>
    <tr><th colspan="5">展開設定を更新する</th></tr>
    <tr><th>更新の種類</th><th>テスト</th><th>第 1</th><th>高速</th><th>広範な質問</th></tr>
    <tr><td>オペレーティング システムの品質更新プログラム</td><td>0 日</td><td>0 日</td><td>0 日</td><td>3 日間</td></tr>
    <tr><td>オペレーティング システムの機能更新プログラム</td><td>0 日</td><td>30 日間</td><td>60 日</td><td>90 日間</td></tr>
    <tr><td>ドライバー/ファームウェア</td><td colspan="4">品質更新プログラムのスケジュールに従う</td></tr>
    <tr><td>ウイルス対策の定義</td><td colspan="4">各スキャンで更新</td></tr>
    <tr><td>Microsoft 365 Apps for enterprise</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">詳細情報</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">詳細情報</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/teams#updates">詳細情報</a></td></tr>
</table>

>[!NOTE]
>これらの延期期間は、すべてのユーザーに対して高いセキュリティとパフォーマンスの標準を確保するために意図的に設計されています。 さらに、すべての Microsoft マネージド デスクトップ デバイスで収集されたデータ、および更新プログラムの範囲と影響に応じて、Microsoft マネージド デスクトップは、任意の展開グループおよびすべての展開グループについて、上記の延期期間の長さをアドホックベースで変更する柔軟性を有します。
>
>Microsoft マネージド デスクトップでは、各 Windows 機能リリースの独立した評価を実施して、管理対象テナントに対する必要性と有用性を評価します。 したがって、Microsoft マネージド デスクトップでは、すべての Windows 機能更新プログラムが展開される場合と展開されない場合があります。 

## <a name="windows-insider-program"></a>Windows Insider Program

Microsoft マネージド デスクトップでは、Windows Insider Program の一部であるデバイスはサポートされていません。 Windows Insider プログラムは、プレリリース版の Windows ソフトウェアを検証するために使用され、ミッション クリティカルではないデバイスを対象とします。 これは Microsoft の重要な取り組みですが、実稼働環境での広範な展開を目的としません。 

Windows Insider ビルドで検出されたデバイスは、テスト グループに含め、更新サービス レベル契約と Microsoft マネージド デスクトップからのユーザー サポートから除外されます。

## <a name="bandwidth-management"></a>帯域幅管理

配信の [最適化は、](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) すべてのオペレーティング システムとドライバーの更新プログラムに使用されます。 これにより、企業ネットワーク内のピアから更新プログラムをシークすることで、Windows Update サービスからのダウンロード サイズを最小限に抑える。

