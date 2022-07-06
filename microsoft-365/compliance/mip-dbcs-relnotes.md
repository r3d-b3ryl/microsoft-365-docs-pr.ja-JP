---
title: 2 バイト文字セットのリリース ノート向け Microsoft Purview サポート
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 2 バイト文字セットをサポートするためのリリース ノートです。
ms.openlocfilehash: 593e1db04c5e4dc56bc4cc1a7fd11d907d4fe09d
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66622427"
---
# <a name="support-for-double-byte-character-set-release-notes"></a>2 バイト文字セットのリリース ノート向けサポート

 Microsoft 365 Information Protection では、次の 2 バイト文字セットの言語がサポートされるようになりました:

- 中国語 (簡体字)
- 中国語 (繁体字)
- 韓国語
- 日本語

このサポートは、機密情報の種類とキーワード ディクショナリで使用でき、Microsoft Purview データ損失防止 (Exchange Online、SharePoint Online、OneDrive for Business、および Teams 用)、 コミュニケーション コンプライアンス、Office アプリの自動ラベル付け、および Microsoft Defender for Cloud Apps に反映されます。

## <a name="known-issues"></a>既知の問題

- メールに添付されているテキスト ファイルが、バイト オーダー マーク (BOM) なしの UTF-8 形式である場合、そのメールはコミュニケーション コンプライアンス ポリシーによって検出されません。

- 「メッセージに次のいずれかの単語が含まれている」というポリシー条件に対して、文が入力されている場合、 コミュニケーション コンプライアンス ポリシーで値を検出することはできません。 ポリシーで指定したテキストが単語として書かれている場合は検出されますが、文章の途中に書かれている場合は検出されません。

- ディクショナリをタイプ情報として指定するコミュニケーション コンプライアンス ポリシーでは、Teams のプライベート チャットやチャネル チャットは検出されません。

- この段階では、次の条件はコミュニケーション コンプライアンスをサポートしていません (将来的にはこのような問題を修正する予定です): 
  - 「メッセージに次のいずれかの単語が含まれている」
  - 「メッセージに次のどの単語も含まれていない」
  - 「添付ファイルに次のいずれかの単語が含まれている」
  - 「添付ファイルに次のいずれかの単語が含まれている」

- データ損失防止ポリシーは、Catalina 10.15以降を搭載したmacOSデバイス（プレビュー）において、日本語を含む東アジア言語に対する下記の条件を除き、強制的に適用されます。
  - 日本の銀行口座番号などの組み込みテンプレートを使用した場合、全角の数字は検出されない
  - 区切り記号のない数値が検出されない
  - 半角スペースで区切られたキーワードは、機密情報の種類として検出されません。 たとえば、日本語は機密情報の種類に設定され、辞書が文中にある場合は検出されません。
  - 英語と日本語 (東京 2020) の両方を含む単語が検出されない

代わりに、ユーザー設定の機密情報の種類 (SIT) を作成することをお勧めします。これは、メッセージと添付ファイル全体のパターンを検出し、通信コンプライアンス ポリシーの条件として使用します。
