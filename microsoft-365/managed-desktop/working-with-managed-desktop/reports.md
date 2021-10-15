---
title: レポートを操作する
description: Microsoft Managed Desktop で利用可能なさまざまなレポート
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 4a0a1d674d14b6569acc07d65ec3f2cc886deeaa
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2021
ms.locfileid: "60364148"
---
# <a name="work-with-reports"></a>レポートを操作する

Microsoft エンドポイント マネージャーコンソールでは、複数の製品からのレポートを 1 つの場所にまとめ、Azure AD 組織 ("テナント") の構成とデバイスに関する問題の監視と調査に役立ちます。 Microsoft Managed desktop には、[レポート] メニューのセクションがあります。このセクションでは、登録したデバイスの Microsoft Managed Desktop の管理に固有のレポートを見つけられます。 さらに、Microsoft エンドポイント マネージャー を通じて複数の場所でレポートをフィルター処理して、Microsoft Managed Desktop で管理されているデバイスを具体的に含めるか除外することもできます。 

## <a name="microsoft-managed-desktop-reports"></a>Microsoft Managed Desktop レポート
Microsoft Managed Desktop には、組織内の IT 管理者がデバイスの人口のさまざまな側面を理解するために使用できるいくつかのレポートとダッシュボードが提供されています。これらのレポートは、管理デバイスの [レポート] メニューの *[Microsoft Managed Desktop]* セクションに移動してMicrosoft エンドポイント マネージャー。 

[概要 **] タブ** には、デバイスの更新に関する簡単な指標が表示されます。 [メトリック **の詳細を表示** する] を選択すると、メトリックの基になるデータセットなど、オフライン分析の追加情報をダウンロードできます。

[レポート] タブ **を選択** すると、使用可能な詳細レポートの説明が表示されます。 これらのレポートは、より包括的で、ポータル内のデータの視覚化とフィルター処理、およびオフライン分析または配布用の基になるデータのエクスポートをサポートします。 現在、次のレポートを利用できます。
- [ [**デバイスの状態]** レポート](device-status-report.md) (*プレビュー*) には、デバイスのアクティビティと使用状況に基づいて Microsoft Managed Desktop サービスの使用が表示されます。 
- デバイスの状態 **の傾向***(プレビュー*) を使用して、Microsoft Managed Desktop デバイスの過去 60 日間のデバイスの状態の傾向を監視できます。 傾向は、デバイスの状態を、新しい展開など、時間の間に他の変更と関連付けるのに役立ちます。 
- [ **[Windows更新プログラム]** レポート](security-updates-report.md)*(プレビュー*) は、Microsoft Windowsデスクトップ デバイス間でセキュリティ更新プログラムがリリースされる方法を示しています。
- アプリケーション [**使用状況レポートには** 、Microsoft](app-usage-report.md) Managed Desktop デバイス全体での一般的なアプリの使用状況に関する情報が表示されます。 デバイスがデータをこのレポートに提供するには、オプションの診断データ レベルに設定する必要があります。

## <a name="endpoint-analytics"></a>エンドポイントの分析
Microsoft Managed Desktop は、エンドポイント分析 [と統合されました](/mem/analytics/overview)。 これらのレポートは、組織の動作状況とユーザーに提供されるエクスペリエンスの品質を測定するための分析情報を提供します。 エンドポイント分析は、エンドポイントの **[レポート**] メニュー [Microsoft エンドポイント マネージャー。](https://endpoint.microsoft.com/) スコアをピボットして、Microsoft Managed Desktop によって管理されているデバイスのみを含めるには、任意のレポートに移動し、[フィルター] ドロップダウンを選択し **、[Microsoft 管理** デスクトップ デバイス] を選択します。

登録中にエンドポイント分析が組織 ("tenant") Azure AD自動的に構成されていない場合は、自分で行います。 詳細については [、「Onboard in the Endpoint analytics portal」を参照してください](/mem/analytics/enroll-intune#bkmk_onboard)。 すべてのデバイスを登録するか、Microsoft Managed Desktop デバイスのみを含める場合は、テスト、First、Fast、および Broad のモダン ワークプレース デバイス グループを選択します。  これらのレポートでは、さまざまなアクセス許可が必要になる場合があります。 詳細については、「アクセス許可」 [を参照](/mem/analytics/overview#permissions) して、役割が適切に割り当てられているか確認してください。

> [!NOTE]
> ユーザーのプライバシーを尊重するには、このフィルターを使用するには、エンドポイント分析に登録されている Microsoft Managed Desktop デバイスが 10 台を超える必要があります。

## <a name="intune-reports"></a>Intune レポート
Microsoft Intuneは、お客様に代わってデバイスを管理するために使用するサービスの 1 つです。 場合によっては、Intune レポートを使用して Microsoft 管理デスクトップ デバイスの管理を具体的に監視すると便利です。 または、他のデバイスの管理に使用するレポートから、管理するデバイスを除外することもできます。 次のレポートでは、Microsoft Managed Desktop デバイスを含めるか除外する機能をフィルター処理できます。

- [すべてのデバイス](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [デバイスのコンプライアンス](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [非準拠デバイス](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Microsoft Managed Desktop のカスタム ロールは、Microsoft Managed Desktop レポートへのアクセスのみを保証します。 すべてのデバイスなど、Microsoft エンドポイント マネージャーの他の部分にアクセスするには、「すべてのデバイスを使用した役割ベースのアクセス[制御」をMicrosoft Intune。](/mem/intune/fundamentals/role-based-access-control) 

## <a name="microsoft-managed-desktop-inventory-data"></a>Microsoft Managed Desktop インベントリ データ

他のレポートに加えて、Microsoft Managed Desktop によって管理されるデバイスに関する情報をエクスポートできます。 [すべての **デバイス]** タブの [デバイス] Microsoft エンドポイント マネージャーで、[すべてエクスポート] タブを使用して詳細なインベントリ レポート [をダウンロードします](device-inventory-report.md)。
