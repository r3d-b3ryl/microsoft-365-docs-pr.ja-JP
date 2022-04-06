---
title: サポート終了のソフトウェアとソフトウェアのバージョンを計画する
description: サポートされなくなった、セキュリティ更新プログラムを受け取らないソフトウェアとソフトウェアのバージョンを検出して計画します。
keywords: 脅威と脆弱性の管理、Microsoft Defender for Endpoint tvm セキュリティ推奨事項、サイバーセキュリティの推奨事項、アクション可能なセキュリティ推奨事項
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3997e2cb372a2cbbbdb0d8e9b51c5b57bd38c7aa
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476689"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a>サポート終了のソフトウェアとソフトウェア のバージョンを計画する場合は、脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

ソフトウェアバージョンまたはソフトウェア バージョンのサポート終了 (EOL) は、サポートまたはサービスが終了し、セキュリティ更新プログラムを受け取らなくなるという意味です。 サポートが終了したソフトウェアまたはソフトウェア バージョンを使用する場合は、セキュリティの脆弱性、法的リスク、財務上のリスクに組織を公開します。

セキュリティと IT 管理者が一緒に作業し、最適な結果、コンプライアンス、および健全なネットワーク エコシステムのために組織のソフトウェア インベントリが構成されていることを確認することが重要です。 サポートが終了し、サポートされなくなったバージョンを更新したアプリを削除または置き換えるオプションを確認する必要があります。 サポート終了日前に計画を作成して実装するのが最善です。

> [!NOTE]
> 現在、サポート終了機能は、現在、一部の製品Windowsできます。

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a>サポートされなくなったソフトウェアまたはソフトウェアのバージョンを検索する

1. [セキュリティ脅威と脆弱性の管理] メニューから、[セキュリティの推奨事項 [**] に移動します**](tvm-security-recommendation.md)。
2. [フィルター] **パネルに移動** し、[タグ] セクションを探します。 1 つ以上の EOS タグ オプションを選択します。 [適用 **] をクリックします**。

   :::image type="content" source="images/tvm-eos-tag.png" alt-text="EOS ソフトウェア、EOS バージョン、および今後の EOS バージョン" lightbox="images/tvm-eos-tag.png":::

3. サポートが終了しているソフトウェア、サポート終了のソフトウェア バージョン、またはサポートが終了するバージョンに関連する推奨事項の一覧が表示されます。 これらのタグは、ソフトウェア インベントリ ページ [にも表示](tvm-software-inventory.md) されます。

   :::image type="content" source="images/tvm-eos-tags-column.png" alt-text="EOS タグを使用した推奨事項" lightbox="images/tvm-eos-tags-column.png":::

## <a name="list-of-versions-and-dates"></a>バージョンと日付の一覧

サポートが終了したバージョンの一覧を表示するには、またはサポートを終了またはすぐにサポートし、それらの日付を表示するには、次の手順を実行します。

1. サポートが終了したバージョンまたはサポートが近日終了するソフトウェアのセキュリティ推奨事項のフライアウトにメッセージが表示されます。

   :::image type="content" source="images/eos-upcoming-eos.png" alt-text="バージョン配布リンク" lightbox="images/eos-upcoming-eos.png":::

2. バージョン配布 **リンクを選択** して、ソフトウェアのドリルダウン ページに移動します。 そこでは、タグがサポートの終了またはサポートの今後の終了として識別される、フィルター処理されたバージョンの一覧を表示できます。

   :::image type="content" source="images/software-drilldown-eos.png" alt-text="サポート ソフトウェアの終了の詳細を示すソフトウェア ドリルダウン ページ" lightbox="images/software-drilldown-eos.png":::

3. 開くテーブルのバージョンのいずれかを選択します。 たとえば、バージョン 10.0.18362.1。 サポート終了日のフライアウトが表示されます。

   :::image type="content" source="images/version-eos-date.png" alt-text="サポート終了日の表示" lightbox="images/version-eos-date.png":::

サポート終了の状態により脆弱なソフトウェアとソフトウェアのバージョンを特定したら、それらを更新するか、組織から削除するか決定する必要があります。 これにより、組織は脆弱性や高度な永続的な脅威にさらされるリスクを軽減します。

## <a name="related-topics"></a>関連項目

- [脅威と脆弱性の管理概要](next-gen-threat-and-vuln-mgt.md)
- [セキュリティ上の推奨事項](tvm-security-recommendation.md)
- [ソフトウェア インベントリ](tvm-software-inventory.md)
