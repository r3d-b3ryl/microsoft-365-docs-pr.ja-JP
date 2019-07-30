---
title: Microsoft マネージドデスクトップでの更新プログラムの処理方法
description: Microsoft Managed Desktop を最新の状態に保つことは、速度と安定性のバランスになります。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7709779c73293a4523bf3cc381d0b59f7fbca325
ms.sourcegitcommit: d137cb1bd67a79d8af84357dc156824830d35aa7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2019
ms.locfileid: "35924870"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップでの更新プログラムの処理方法


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft マネージドデスクトップは、すべてのデバイスを最新のクラウドベースのインフラストラクチャに接続します。 ビジネスアプリケーションの更新プログラムについては、Windows、Office、ドライバー、ファームウェア、Microsoft Store を最新の状態に維持することで、速度と安定性のバランスが保たれます。 展開グループは、OS とポリシーが安全な方法でロールアウトされるようにするために使用されます。 

Microsoft によってリリースされた更新プログラムは累積的であり、品質または機能の更新プログラムとして分類されます。
詳細については、「 [Windows update For Business: update types](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)」を参照してください。 

## <a name="update-groups"></a>グループを更新する

Microsoft マネージドデスクトップでは、次の4つの Azure AD グループを使用して更新を管理します。

- **テスト**: Microsoft Managed Desktop policy の変更、OS 更新プログラム、機能の更新プログラム、その他の変更をテナントにプッシュ配信するために使用します。 テストグループには、エンドユーザーが配置されていない必要があります。 テストグループは、確立された Sla およびエンドユーザーサポートの対象外です。 このグループは、新しいポリシーまたは OS の変更によるアプリケーションの互換性を検証するために使用できます。  
- **最初**の段階では、プレリリース版の更新プログラムの対象となる初期のソフトウェア導入とデバイスが含まれています。 このグループ内のデバイスでは、テスト時に対象としていないシナリオがある場合は停止する可能性があります。
- **Fast**: 安定性を優先して速度を優先します。 広範なグループに提供される前に品質の問題を検出するのに役立ちます。 このグループは、次の検証層として機能しますが、通常はテストと最初のグループよりも安定しています。 
- **広範**: 最後のグループは、機能と品質の更新を利用できるようにします。 このグループには、テナント内のユーザーの大部分が含まれているため、展開時の安定性が向上します。 この環境は最も安定しているため、アプリのテストを行う必要があります。 

このような展開グループの役割と責任の詳細については、「Microsoft の管理された[デスクトップの役割と責任](../intro/roles-and-responsibilities.md)」を参照してください。

更新プログラムの展開のしくみは次のとおりです。
- Microsoft マネージドデスクトップでは、次に示すスケジュールに従って、新しい機能または品質更新が展開されます。
- 展開時に、Microsoft マネージドデスクトップは、診断データの信号とエンドユーザーのサポートシステムに基づいて、障害または停止の兆候を監視します。 いずれかが検出された場合は、現在のグループと今後のグループのすべてに対する展開が直ちに一時停止されます。
    - 例: 最初のグループに品質の更新プログラムを展開しているときに問題が検出された場合、最初のグループへの展開、Fast、および広範な更新は、問題が解決されるまで一時停止します。
    - 互換性の問題は、Microsoft Managed Desktop IT 管理ポータルにチケットをファイリングすることで報告できます。
- 機能と品質の更新は個別に一時停止されます。 既定では、一時停止は35日間有効になりますが、問題が改善されたかどうかに応じて、縮小または拡張できます。
- グループが一時停止すると、次のスケジュールに従って展開が再開されます。
- この展開プロセスは、機能と品質更新プログラムの両方に適用されます。ただし、タイムラインはそれぞれに異なります。

<table>
<tr><th colspan="5">展開設定を更新する</th></tr>
<tr><th>更新の種類</th><th>テスト</th><th>第 1</th><th>高速</th><th>広範な質問</th></tr>
<tr><td>オペレーティングシステムの品質更新プログラム</td><td>0日</td><td>0日</td><td>0日</td><td>3 日間</td></tr>
<tr><td>オペレーティングシステムの機能更新プログラム</td><td>0日</td><td>30 日間</td><td>60 日</td><td>90 日間</td></tr>
<tr><td>ドライバー/ファームウェア</td><td colspan="4">品質更新プログラムのスケジュールに従います。</td></tr>
<tr><td>ウイルス対策の定義</td><td colspan="4">各スキャンで更新</td></tr>
</table>

>[!NOTE]
>この遅延期間は、すべてのユーザーに対して高セキュリティとパフォーマンス標準を確実にするために意図的に設計されています。 さらに、Microsoft マネージドデスクトップのすべてのデバイスで収集されたデータと、更新のさまざまな範囲と影響に基づいて、Microsoft マネージドデスクトップは、ad 上のすべての展開グループに対して上記の遅延期間の長さを変更するための柔軟性を確保します。hoc。
>
>Microsoft マネージドデスクトップでは、管理されたテナントに対して、その必要性と有用性を評価するために、各 Windows 機能のリリースに対して個別の評価を実施しています。 そのため、Microsoft マネージドデスクトップは、Windows のすべての機能の更新プログラムを展開する場合としない場合があります。 

## <a name="windows-insider-program"></a>Windows Insider Program

Microsoft マネージドデスクトップでは、Windows Insider program の一部であるデバイスはサポートされていません。 Windows Insider プログラムは、プレリリース版の Windows ソフトウェアを検証するために使用され、ミッションクリティカルではないデバイスを対象としています。 これは重要な Microsoft イニシアチブですが、運用環境での幅広い展開を目的としたものではありません。 

Windows Insider ビルドで見つかったすべてのデバイスはテストグループに配置され、Microsoft マネージドデスクトップからのサービスレベル契約 (Sla) とエンドユーザーサポートの対象外となります。

## <a name="bandwidth-management"></a>帯域幅管理

配信の最適化は、すべてのオペレーティングシステムとドライバーの更新に使用されます。 これにより、企業ネットワーク内のピアから更新を検索することによって、Windows Update サービスからのダウンロードサイズを最小限に抑えることができます。


