---
title: レポートを操作する
description: Microsoft Managed Desktop で利用可能なさまざまなレポート
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 620e9d2bd95dc4782237af94966b5cb52579b656
ms.sourcegitcommit: 19e16b16f144159b55bb4c544403e3642b69e335
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2022
ms.locfileid: "62818578"
---
# <a name="work-with-reports"></a>レポートを操作する

Microsoft エンドポイント マネージャー コンソールは、複数の製品からのレポートを 1 つの場所にまとめ、Azure AD 組織 ("tenant") 構成とデバイスの問題を監視および調査するのに役立ちます。

Microsoft Managed Desktop には、[レポート] メニューのセクションがあります。このセクションでは、登録済みデバイスの Microsoft Managed Desktop の管理に固有のレポートを見つけられます。 複数の場所で、Microsoft エンドポイント マネージャーグループからレポートをフィルター処理できます。 Microsoft Managed Desktop によって管理されているデバイスを含めるか除外できます。

## <a name="microsoft-managed-desktop-reports"></a>Microsoft Managed Desktop レポート

Microsoft Managed Desktop には、いくつかのレポートとダッシュボードがあります。 組織の IT 管理者は、これらのレポートとダッシュボードを使用して、デバイスの人口のさまざまな側面を理解できます。 [Microsoft エンドポイント マネージャー] セクションに移動し、[Microsoft Managed Desktop] の下の [管理対象デバイス] を選択します。

[概要 **] タブ** には、デバイスの更新に関する簡単な指標が表示されます。 [ **メトリックの詳細** を表示する] を選択して、メトリックの基になるデータセットを含むオフライン分析の追加情報をダウンロードします。

[レポート] タブ **を選択** すると、使用可能な詳細レポートの説明が表示されます。 これらのレポートは、より包括的で、ポータルでのデータの視覚化とフィルター処理をサポートします。 基になるデータをオフライン分析または配布用にエクスポートすることもできます。 現在、次のレポートを利用できます。

| レポート | 説明 |
| ------ | ------ |
| [**デバイスの状態** レポート](device-status-report.md) (*プレビューで*) | このレポートには、デバイスのアクティビティと使用状況に基づく Microsoft Managed Desktop サービスの使用が表示されます。 |
| **デバイスの状態の傾向** (*プレビューで*) | これは、Microsoft Managed Desktop デバイスの過去 60 日間のデバイスの状態の傾向を監視します。 傾向は、デバイスの状態を、新しい展開など、時間の間に他の変更と関連付けるのに役立ちます。 |
| [**Windows更新レポート** (](security-updates-report.md)*プレビュー)* | このレポートでは、Microsoft Windowsデスクトップ デバイス間でセキュリティ更新プログラムがどのようにリリースされるのかについて説明します。 |
| [**アプリケーション使用状況** レポート](app-usage-report.md) | このレポートでは、Microsoft Managed Desktop デバイス全体での一般的なアプリの使用状況に関する情報を提供します。 デバイスがデータをこのレポートに提供するには、オプションの診断データ レベルに設定する必要があります。 |
| [**サービス メトリックス レポート**](service-metrics-report.md) (*プレビュー)* | このレポートでは、Microsoft Managed Desktop の主要な指標を月単位で簡単に要約できます。 |

## <a name="endpoint-analytics"></a>エンドポイントの分析

Microsoft Managed Desktop は、エンドポイント分析 [と統合されました](/mem/analytics/overview)。 これらのレポートは、組織の動作状況とユーザーに提供されるエクスペリエンスの品質を測定するための分析情報を提供します。 エンドポイント分析は、エンドポイントの [レポート] **メニュー Microsoft エンドポイント マネージャー。** [](https://endpoint.microsoft.com/) スコアをピボットして Microsoft Managed Desktop によって管理されているデバイスのみを含めるには、任意のレポートに移動し、[フィルター] ドロップダウンを選択し、[**Microsoft 管理** デスクトップ デバイス] を選択します。

登録中にエンドポイント分析が Azure AD組織 ("tenant") に対して自動的に構成されていない場合は、自分で行います。 詳細については、「 [Onboard in the Endpoint analytics portal」を参照してください](/mem/analytics/enroll-intune#bkmk_onboard)。 すべてのデバイスを登録するか、Microsoft Managed Desktop デバイスのみを含める場合は、Test、First、Fast、および Broad  のモダン ワークプレース デバイス グループを選択します。 これらのレポートでは、さまざまなアクセス許可が必要になる場合があります。 詳細については、「アクセス許可」 [を参照](/mem/analytics/overview#permissions) して、役割が適切に割り当てられているか確認してください。

> [!NOTE]
> ユーザーのプライバシーを尊重するには、このフィルターを使用するには、エンドポイント分析に登録されている Microsoft Managed Desktop デバイスが 10 台を超える必要があります。

## <a name="intune-reports"></a>Intune レポート

Microsoft Intuneは、お客様に代わってデバイスを管理するために使用するサービスの 1 つです。

場合によっては、Intune レポートを使用して Microsoft 管理デスクトップ デバイスの管理を具体的に監視すると便利です。 他のデバイスの管理に使用するレポートから、管理するデバイスを除外できます。 次のレポートでは、Microsoft Managed Desktop デバイスを含めるか除外する機能をフィルター処理できます。

- [すべてのデバイス](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [デバイスのコンプライアンス](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [非準拠デバイス](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Microsoft Managed Desktop のカスタム ロールは、Microsoft Managed Desktop レポートへのアクセスのみを保証します。 すべてのデバイスなど、Microsoft エンドポイント マネージャーの他の部分にアクセスするには、「すべてのデバイスを使用した役割ベース[のアクセス制御」をMicrosoft Intune](/mem/intune/fundamentals/role-based-access-control)。

## <a name="microsoft-managed-desktop-inventory-data"></a>Microsoft Managed Desktop インベントリ データ

他のレポートに加えて、Microsoft Managed Desktop によって管理されるデバイスに関する情報をエクスポートできます。 [Microsoft エンドポイント マネージャーに移動し、[デバイス] セクションの [Microsoft Managed Desktop] で、[デバイス]  を選択し、[すべてエクスポート] タブを使用して詳細なインベントリ レポート[をダウンロードします](device-inventory-report.md)。
