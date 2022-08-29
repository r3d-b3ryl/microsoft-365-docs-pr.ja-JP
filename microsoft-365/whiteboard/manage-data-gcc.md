---
title: GCC 環境で Microsoft Whiteboard のデータを管理する
ms.author: v-jdeweese
author: johnddeweese
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
ms.openlocfilehash: 2d6fd5c6c0ebd0b11e06e7575a1e121b089de065
ms.sourcegitcommit: 031b3e963478f642a0d23be37a01f23a01cb3d84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2022
ms.locfileid: "67441922"
---
# <a name="manage-data-for-microsoft-whiteboard-in-gcc-environments"></a>GCC 環境で Microsoft Whiteboard のデータを管理する

>[!NOTE]
> このガイダンスは、米国政府機関コミュニティ クラウド (GCC) 環境に適用されます。

データは、OneDrive for Businessに .whiteboard ファイルとして格納されます。 平均的なホワイトボードのサイズは 50 KB から 1 MB で、OneDrive for Business コンテンツが存在する場所であればどこでも配置できます。 新しいデータが作成される場所を確認するには、「 [Microsoft 365 顧客データの保存場所」を参照してください](/microsoft-365/enterprise/o365-data-locations)。 OneDrive for Businessの場所を確認します。 OneDrive for Businessの一般的なファイルに適用されるすべてのプロパティは、外部共有を除く Whiteboard にも適用されます。

データを管理するには、まず組織で Whiteboard が有効になっていることを確認する必要があります。 詳細については、「 [GCC High 環境での Whiteboard へのアクセスの管理](manage-whiteboard-access-gcc-high.md)」を参照してください。

既存のOneDrive for Business コントロールを使用してホワイトボード データを管理できます。 詳細については、 [企業向けの OneDrive ガイドを参照してください](/onedrive/plan-onedrive-enterprise)。

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
- SharePoint サイトへのホワイトボードの保存

## <a name="see-also"></a>関連項目

[Whiteboard へのアクセスを管理する - GCC High](manage-whiteboard-access-gcc-high.md)

[Whiteboard の共有を管理する - GCC High](manage-sharing-gcc-high.md)

[Whiteboard のクライアントを管理する - GCC High](manage-clients-gcc-high.md)
