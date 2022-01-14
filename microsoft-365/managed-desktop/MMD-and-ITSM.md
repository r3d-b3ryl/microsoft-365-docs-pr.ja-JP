---
title: Microsoft マネージド デスクトップと ITIL (IT インフラストラクチャ ライブラリ)
description: ITIL フェーズと Microsoft Managed Desktop の情報と記事を関連付ける
keywords: Microsoft Managed Desktop、Microsoft 365、サービス、ドキュメント、ITISM
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: b9984e308b6681512297e484817f95206283385e
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035090"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft マネージド デスクトップと ITIL (IT インフラストラクチャ ライブラリ)

多くの組織では [、ITIL](https://www.axelos.com/best-practice-solutions/itil)などの正式な IT サービス モデル (ITSM) のラインに沿って IT サービスを構造化する価値があります。 

Microsoft Managed Desktop を使用すると、組織はこのような形式化された ITSM モデルの多くの重要な側面に準拠できます。 ITIL を例として使用すると、この記事では、一般的な ITIL フェーズとプロセス、および同等の Microsoft マネージ デスクトップ機能 (該当する場合) の接続を確認できます。 この情報は、組織の Microsoft Managed Desktop 部分にのみ適用されます。

ITIL とそのフェーズとプロセスの詳細については、ドキュメントを参照 [してください](https://www.axelos.com/best-practice-solutions/itil)。


## <a name="service-design"></a>サービス設計

次の表は、ITIL の主要なフェーズとプロセスを Microsoft Managed Desktop の機能に関連付け、詳細についてはドキュメントへのリンクを参照してください。



|ITIL プロセス |説明  |ドキュメント |
|---------|---------|---------|
|サービス レベルの管理     | 応答時間は、管理者サポート要求とインシデントに対して定義されます。  |  [Microsoft マネージド デスクトップの管理者サポート](working-with-managed-desktop/admin-support.md)  |
|サービス カタログの管理     | サービスのコンポーネントを詳細に説明するサービスの説明は、現在および関心のあるすべての顧客が利用できるサービスの状態に対応します。<br><br>サービスの運用に必要な情報を理解するために詳しく説明されている前提条件。  | - [Microsoft Managed Desktop サービスの説明](service-description/index.md)<br><br>- [Microsoft Managed Desktop での登録の準備をする](get-ready/index.md)  |
|情報セキュリティ管理     | サービスの情報セキュリティを含むセキュリティ情報。<br><br> セキュリティ関連のポリシーと、デバイスの構成方法に関するその他の情報。   | - [Microsoft Managed Desktop のセキュリティ](service-description/security.md)<br><br>- [デバイス構成](service-description/device-policies.md)  |
|可用性の管理     |  Microsoft Managed Desktop は、サービスの可用性を確保するために、組織と責任をバランスよく管理します。<br><br>サービスまたは可用性の問題がある場合、管理者とユーザーはそれぞれのサポートへのルートを持っています。 | - [Microsoft Managed Desktop の操作と監視](service-description/operations-and-monitoring.md)<br><br>- [Microsoft Managed Desktop の管理者サポート](working-with-managed-desktop/admin-support.md)<br>- [ユーザーのヘルプの取得](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>サービス移行


|ITIL プロセス |説明  |ドキュメント |
|---------|---------|---------|
|変更管理     | 利用可能な変更管理に関連する責任、プロセスの概要、および種類の定義されたバランス。  | [Microsoft Managed Desktop の操作と監視](service-description/operations-and-monitoring.md#change-management) |
|リリースと展開の管理     |  Microsoft Managed Desktop は、サービスに登録されているデバイスの更新プログラムを管理します。  | [Microsoft Managed Desktop での更新プログラムの処理方法](service-description/updates.md)        |
|サービス資産と構成管理     | 組織の Microsoft Managed Desktop 展開に関する情報は、IT 管理ポータルで確認できます。  | [Microsoft マネージド デスクトップの管理者サポート](working-with-managed-desktop/admin-support.md) |
|ナレッジ管理     | Microsoft Managed Desktop サービスに関する情報は、このサイトで最新の状態に維持されます。   | [Microsoft マネージド デスクトップのドキュメントの変更履歴](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>サービス操作


|ITIL プロセス |説明  |ドキュメント  |
|---------|---------|---------|
|イベント管理     |  デバイスの監視に関する詳細が提供されます。<br><br>Microsoft Managed Desktop サービスの標準的な操作手順について詳しく説明します。 |  - [Microsoft Managed Desktop のセキュリティ](service-description/security.md)<br>- [Microsoft Managed Desktop の操作と監視](service-description/operations-and-monitoring.md)       |
|インシデント管理  | Microsoft Managed Desktop は、定義された重大度定義ごとのインシデントを調査して処理します。  |  [要求の重大度の定義をサポートする](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|フルフィルメント管理の要求     |  Microsoft Managed Desktop サービスに関連する情報要求および変更要求のプロセスが定義されています。         |[Microsoft マネージド デスクトップの管理者サポート](working-with-managed-desktop/admin-support.md)         |
|問題の管理     | サービスに関する問題は、現時点でローカル アカウント チームに指示する必要があります。 | 開発中のドキュメント |
|アクセス管理     | 機能の詳細を確認するために、お客様の管理コンポーネントと責任にアクセスします。  | [ID およびアクセス管理](service-description/security.md#identity-and-access-management)        |
