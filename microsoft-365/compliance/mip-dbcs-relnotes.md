---
title: 2 バイト文字セットのリリース ノート向け Microsoft 365 コンプライアンス サポート (プレビュー)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 2 バイト文字セットをサポートするためのリリース ノートです。
ms.openlocfilehash: 1c2244c49a92aa2c00fad06caa8194cf7e32220e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681503"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a>2 バイト文字セットのリリース ノート向けサポート (プレビュー)

 Microsoft 365 の情報保護は、次のような場合に 2 バイト文字セットの言語をプレビューでサポートしています。

- 中国語 (簡体字)
- 中国語 (繁体字)
- 韓国語
- 日本語

このサポートは、機密情報の種類とキーワード ディクショナリで使用でき、データ損失防止、通信コンプライアンス、Exchange Online、SharePoint Online、OneDrive for Business、および Teams ソリューションに反映されます。

## <a name="known-issues"></a>既知の問題

- メールに添付されているテキスト ファイルが、バイト オーダー マーク (BOM) なしの UTF-8 形式である場合、そのメールは通信コンプライアンス ポリシーで検出されません。

- 「メッセージに次のいずれかの単語が含まれている」というポリシー条件に対して、文が入力されている場合、通信コンプライアンス ポリシーで値を検出することはできません。 ポリシーで指定したテキストが単語として書かれている場合は検出されますが、文章の途中に書かれている場合は検出されません。

- ディクショナリをタイプ情報として指定する通信コンプライアンス ポリシーでは、Teams のプライベート チャットやチャネル チャットは検出されません。

- この段階では、次の条件は通信コンプライアンスをサポートしていません (将来的にはこのような問題を修正する予定です)。 
  - 「メッセージに次のいずれかの単語が含まれている」
  - 「メッセージに次のどの単語も含まれていない」
  - 「添付ファイルに次のいずれかの単語が含まれている」
  - 「添付ファイルに次のいずれかの単語が含まれている」

代わりに、ユーザー設定の機密情報の種類 (SIT) を作成することをお勧めします。これは、メッセージと添付ファイル全体のパターンを検出し、通信コンプライアンス ポリシーの条件として使用します。
