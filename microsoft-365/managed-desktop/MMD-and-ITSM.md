---
title: Microsoft マネージド デスクトップと ITIL (IT インフラストラクチャ ライブラリ)
description: ITIL フェーズと Microsoft マネージド デスクトップの情報および記事を関連付ける
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント、ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: e545b64670bb92c40465f1c50b2cb46b9fd7a8d8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841437"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft マネージド デスクトップと ITIL (IT インフラストラクチャ ライブラリ)

多くの組織では [、ITIL](https://www.axelos.com/best-practice-solutions/itil)などの正式な IT サービス モデル (ITSM) のラインに沿って IT サービスを構築する価値があります。 

Microsoft マネージド デスクトップを使用すると、組織はこのような正式な ITSM モデルの多くの重要な側面に準拠できます。 この記事では、ITIL を例として使用して、一般的な ITIL フェーズとプロセス、および同等の Microsoft マネージド デスクトップ機能 (該当する場合) との間の接続を確認するのに役立ちます。 この情報は、組織の Microsoft マネージド デスクトップ部分にのみ適用されます。

ITIL とそのフェーズとプロセスの詳細については、ドキュメントを参照 [してください](https://www.axelos.com/best-practice-solutions/itil)。


## <a name="service-design"></a>サービス設計

次の表は、ITIL の主要なフェーズとプロセスを Microsoft マネージド デスクトップ機能に関連付け、詳細についてはドキュメントへのリンクを示しています。



|ITIL プロセス |説明  |ドキュメント |
|---------|---------|---------|
|サービス レベルの管理     | 応答時間は、管理者サポート要求とインシデントに対して定義されます。  |  [Microsoft マネージド デスクトップの管理者サポート](working-with-managed-desktop/admin-support.md)  |
|サービス カタログの管理     | サービスのコンポーネントを詳細に説明するサービスの説明は、現在および関心のあるすべてのお客様が利用できる、サービスの状態に応じて維持されます。<br><br>サービスを運用するために何が必要かを理解するために詳細に説明された前提条件。  | - [Microsoft マネージド デスクトップ サービスの説明](service-description/index.md)<br><br>- [Microsoft マネージド デスクトップに登録する準備をする](get-ready/index.md)  |
|情報セキュリティ管理     | サービスの情報セキュリティを含むセキュリティ情報。<br><br> セキュリティ関連のポリシーと、デバイスの構成方法に関するその他の情報。   | - [Microsoft マネージド デスクトップのセキュリティ](service-description/security.md)<br><br>- [デバイス構成](service-description/device-policies.md)  |
|可用性管理     |  Microsoft マネージド デスクトップは、サービスの可用性を確保するために、お客様の組織と責任のバランスを取っています。<br><br>サービスまたは可用性に問題がある場合、管理者とユーザーはそれぞれのサポートへのルートを持っています。 | - [Microsoft マネージド デスクトップの操作と監視](service-description/operations-and-monitoring.md)<br><br>- [Microsoft マネージド デスクトップの管理者サポート](working-with-managed-desktop/admin-support.md)<br>- [ユーザー向けヘルプの取得](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>サービスの移行


|ITIL プロセス |説明  |ドキュメント |
|---------|---------|---------|
|変更管理     | 利用可能な変更管理に関連する責任の定義済みのバランス、プロセスの概要、および種類。  | [Microsoft マネージド デスクトップの操作と監視](service-description/operations-and-monitoring.md#change-management) |
|リリースと展開の管理     |  Microsoft マネージド デスクトップは、サービスに登録されているデバイスの更新プログラムを管理します。  | [Microsoft マネージド デスクトップでの更新プログラムの処理方法](service-description/updates.md)        |
|サービス資産と構成の管理     | 組織の Microsoft マネージド デスクトップ展開に関する情報は、IT 管理ポータルで確認できます。  | [Microsoft マネージド デスクトップの管理者サポート](working-with-managed-desktop/admin-support.md) |
|ナレッジ マネジメント     | Microsoft マネージド デスクトップ サービスに関する情報は、このサイトで最新の状態に維持されます。   | [Microsoft マネージド デスクトップのドキュメントの変更履歴](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>サービス操作


|ITIL プロセス |説明  |ドキュメント  |
|---------|---------|---------|
|イベント管理     |  デバイスの監視に関する詳細が提供されます。<br><br>Microsoft マネージド デスクトップ サービスの標準的な運用手順について詳しく説明します。 |  - [Microsoft マネージド デスクトップのセキュリティ](service-description/security.md)<br>- [Microsoft マネージド デスクトップの操作と監視](service-description/operations-and-monitoring.md)       |
|インシデント管理  | Microsoft マネージド デスクトップは、定義された重大度定義ごとのインシデントを調査し、対応します。  |  [要求の重要度の定義をサポートする](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|要求フルフィルメント管理     |  Microsoft マネージド デスクトップ サービスに関連する情報要求および変更要求のプロセスが定義されています。         |[Microsoft マネージド デスクトップの管理者サポート](working-with-managed-desktop/admin-support.md)         |
|問題の管理     | サービスに関する問題は、この時点でローカル アカウント チームに指示する必要があります。 | 開発中のドキュメント |
|アクセス管理     | 機能を確実に詳細に扱うお客様のアクセス管理コンポーネントと責任。  | [ID およびアクセス管理](service-description/security.md#identity-and-access-management)        |
