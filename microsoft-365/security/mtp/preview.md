---
title: Microsoft の脅威保護のプレビュー機能
description: Microsoft 365 セキュリティの新機能について説明します。
keywords: preview、new、m365 security、security、365、capabilities
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 45bc42e825c55ca228b13e8d308f9a1384301d07
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2020
ms.locfileid: "45048269"
---
# <a name="microsoft-threat-protection-preview-features"></a>Microsoft Threat Protection のプレビュー機能

**適用対象:**
- Microsoft Threat Protection


Microsoft Threat Protection サービスは、新しい機能の拡張と機能を含むように、絶えず更新されています。

Microsoft Threat Protection プレビューリリースの新機能について説明し、プレビューの操作をオンにして、最初に予定されている機能を試すことができます。

一般的に利用可能な新機能の詳細については、「[Microsoft Threat Protection の新機能](whats-new.md)」を参照してください。

## <a name="turn-on-preview-features"></a>プレビュー機能を有効にする
機能が一般に利用可能になるまでの全体的な操作を改善するためにフィードバックできる、今後提供される機能にアクセスできるようになります。

[プレビュー環境] 設定をオンにして、最初の機能を試すことができます。

1. ナビゲーションウィンドウで、[**設定**] を選択します。

2. [ **Microsoft Threat Protection**] を選択します。


3. [**プレビュー機能の選択]**  >  **プレビュー機能を有効に**します。 

3. [**保存**] を選択します。

[**プレビュー機能を有効に**する] チェックボックスがオンになっている場合は、プレビュー機能が有効になっていることを確認できます。 

## <a name="preview-features"></a>プレビュー機能
現在、次の機能と拡張機能をプレビューで利用できます。

- **[ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**: セキュリティセンターで直接使用できるスキーマテーブルに関する情報。 このリファレンスでは、テーブルと列の説明に加えて、サポートされているイベントの種類 ( `ActionType` 値) とサンプルクエリに関する情報を提供します。  

- **[Id およびアプリテーブル](advanced-hunting-schema-tables.md)**—高度な検索スキーマにある、ユーザーの認証[イベント、Active](advanced-hunting-identityqueryevents-table.md)Directory クエリ、アプリ[関連のアクティビティ](advanced-hunting-identitylogonevents-table.md)に関する可視性を高める[AppFileEvents](advanced-hunting-appfileevents-table.md)ことができます。

- **[ハントの移動](advanced-hunting-go-hunt.md)**—クエリベースの[高度な](advanced-hunting-overview.md)検索機能を使用して、特定のイベント、ユーザー、デバイス、またはその他のエンティティの種類を調査するために、インシデントの調査からすばやくピボットします。

- **[Fileprofile () 関数](advanced-hunting-fileprofile-function.md)**:[高度な](advanced-hunting-overview.md)検索クエリで使用して、包括的なファイル情報を組み込みます。
