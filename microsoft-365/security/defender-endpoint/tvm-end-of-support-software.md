---
title: サポート終了のソフトウェアとソフトウェアのバージョンを計画する
description: サポートされなくなったソフトウェアとソフトウェアのバージョンを検出して計画し、セキュリティ更新プログラムを受け取りません。
keywords: 脅威と脆弱性の管理、Microsoft Defender for Endpoint tvm セキュリティに関する推奨事項、サイバーセキュリティの推奨事項、実用的なセキュリティに関する推奨事項
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
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a>脅威と脆弱性の管理を使用して、サポート終了のソフトウェアとソフトウェアのバージョンを計画する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

ソフトウェアまたはソフトウェアのバージョンでは、サポート終了 (EOS)、それ以外の場合はエンド オブ ライフ (EOL) と呼ばれます。つまり、サポートやサービスが提供されなくなり、セキュリティ更新プログラムは受け取られません。 ソフトウェアまたはソフトウェアのバージョンをサポート終了と共に使用すると、組織はセキュリティの脆弱性、法的リスク、財務上のリスクにさらされます。

セキュリティと IT 管理者が連携し、組織のソフトウェア インベントリが最適な結果、コンプライアンス、および正常なネットワーク エコシステム用に構成されていることを確認することが重要です。 サポート終了に達したアプリを削除または置き換え、サポートされなくなったバージョンを更新するオプションを確認する必要があります。 サポート終了日の **前** にプランを作成して実装することをお勧めします。

> [!NOTE]
> 現在、サポート終了機能は、Windows製品でのみ使用できます。

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a>サポートされなくなったソフトウェアまたはソフトウェアのバージョンを検索する

1. 脅威と脆弱性の管理 メニューから、[[**セキュリティに関する推奨事項]**](tvm-security-recommendation.md) に移動します。
2. **[フィルター**] パネルに移動し、[タグ] セクションを探します。 1 つ以上の EOS タグ オプションを選択します。 次に **、適用します**。

   :::image type="content" source="images/tvm-eos-tag.png" alt-text="EOS ソフトウェア、EOS バージョン、および今後の EOS バージョン" lightbox="images/tvm-eos-tag.png":::

3. サポートが終了したソフトウェアに関連する推奨事項の一覧、サポート終了のソフトウェア バージョン、または今後サポートが終了するバージョンの一覧が表示されます。 これらのタグは、 [ソフトウェア インベントリ](tvm-software-inventory.md) ページにも表示されます。

   :::image type="content" source="images/tvm-eos-tags-column.png" alt-text="EOS タグを使用したおすすめ" lightbox="images/tvm-eos-tags-column.png":::

## <a name="list-of-versions-and-dates"></a>バージョンと日付の一覧

サポートが終了したバージョンの一覧を表示するには、次の手順に従います。

1. サポートが終了したバージョンのソフトウェアのセキュリティに関する推奨事項ポップアップにメッセージが表示されるか、サポートが間もなく終了します。

   :::image type="content" source="images/eos-upcoming-eos.png" alt-text="バージョン配布リンク" lightbox="images/eos-upcoming-eos.png":::

2. **バージョン配布** リンクを選択して、ソフトウェアのドリルダウン ページに移動します。 そこでは、サポートの終了またはサポートの今後の終了として識別されるタグを含む、フィルター処理されたバージョンの一覧を確認できます。

   :::image type="content" source="images/software-drilldown-eos.png" alt-text="サポート ソフトウェアの終了の詳細を含むソフトウェアのドリルダウン ページ" lightbox="images/software-drilldown-eos.png":::

3. 開くテーブル内のいずれかのバージョンを選択します。 たとえば、バージョン 10.0.18362.1 です。 サポート終了日にポップアップが表示されます。

   :::image type="content" source="images/version-eos-date.png" alt-text="サポート終了日の表示" lightbox="images/version-eos-date.png":::

サポート終了の状態が原因で脆弱なソフトウェアとソフトウェアのバージョンを特定したら、それらを組織で更新するか、組織から削除するかを決定する必要があります。 これを行うと、組織が脆弱性や高度な永続的な脅威にさらされることが減ります。

## <a name="related-topics"></a>関連項目

- [脅威と脆弱性の管理の概要](next-gen-threat-and-vuln-mgt.md)
- [セキュリティに関する推奨事項](tvm-security-recommendation.md)
- [ソフトウェア インベントリ](tvm-software-inventory.md)
