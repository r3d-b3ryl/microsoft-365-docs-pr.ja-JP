---
title: GCC High 環境でMicrosoft Whiteboardのデータを管理する
ms.author: chucked
author: chuckedmonson
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Whiteboard へのアクセスを有効、無効、管理する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e5c0041423a89f5336e5797a5c68d48178cae6a0
ms.sourcegitcommit: b0b1be67de8f40b199bb9b51eb3568e59377e93a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2022
ms.locfileid: "66159870"
---
# <a name="manage-data-for-microsoft-whiteboard-in-gcc-high-environments"></a>GCC High 環境でMicrosoft Whiteboardのデータを管理する

>[!NOTE]
> このガイダンスは、米国Government Community Cloud (GCC) の高い環境に適用されます。

データは、OneDrive for Businessに .whiteboard ファイルとして格納されます。 平均的なホワイトボードのサイズは 50 KB から 1 MB で、OneDrive for Business コンテンツが存在する場所であればどこでも配置できます。 新しいデータが作成される場所を確認するには、「[Microsoft 365顧客データが格納されている場所](/microsoft-365/enterprise/o365-data-locations)」を参照してください。 OneDrive for Businessの場所を確認します。 OneDrive for Businessの一般的なファイルに適用されるすべてのプロパティは、外部共有を除く Whiteboard にも適用されます。

既存のOneDrive for Business コントロールを使用してホワイトボード データを管理できます。 詳細については、[企業向けのOneDrive ガイドを参照してください](/onedrive/plan-onedrive-enterprise)。

既存のOneDrive for Business ツールを使用して、一般データ保護規則 (GDPR) のデータ主体要求 (DSR) を満たすことができます。 ホワイトボード ファイルは、OneDrive for Businessの他のコンテンツと同じ方法で移動できます。 ただし、共有リンクとアクセス許可が移動しない可能性があります。

## <a name="data-controls-supported"></a>サポートされているデータ コントロール

現在、Whiteboard では次のデータ コントロールがサポートされています。

- アイテム保持ポリシー
- Quota
- DLP
- 電子情報開示
- 訴訟ホールド

## <a name="data-controls-planned"></a>計画されたデータ コントロール

Whiteboard の今後のリリースでは、次のデータ コントロールが予定されています。

- 秘密度ラベル
- 監査
- 分析
- SharePoint サイトにホワイトボードを格納する

## <a name="see-also"></a>関連項目

[Whiteboard へのアクセスを有効にして管理する - GCC High](enable-whiteboard-access-gcc-high.md)

[ホワイトボードの共有を管理する - GCC High](manage-sharing-gcc-high.md)

[Whiteboard のクライアントを管理する - GCC High](manage-clients-gcc-high.md)
