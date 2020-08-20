---
title: Microsoft セキュア スコアの新機能
description: Microsoft 365 セキュリティ センターで Microsoft セキュア スコアが新しく変更されたされた内容について説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュア スコア、セキュリティ センター、改善のための処置
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 644e12d3b9dfecc0a31c8d464033e41670bc7b88
ms.sourcegitcommit: 22fd8517707ed3ab6ef996247ad2aa372535ee56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46815233"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft セキュア スコアの新機能

Microsoft セキュア スコアをお客様のセキュリティの状態をよりよく理解するために、いくつかの変更を加えました。 計画された変更については、Microsoft セキ[ュア スコアの新機能を参照してください。](microsoft-secure-score-whats-coming.md)

## <a name="july-2020"></a>2020 年7 月

### <a name="adding-improvement-actions-for-azure-advanced-threat-protection"></a>Azure Advanced Threat Protection の改善のための処置を追加

- 危険なリアル移動パス
- セキュリティで保護されていないアカウントの属性
- Active Directory 信頼のセキュリティ機能を有効にする
- セキュリティで保護されていない SID の履歴属性をエンティティから削除する

## <a name="june-2020"></a>2020 年 6 月

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection の改善アクションの削除

* 攻撃表面の縮小ルールを有効にする

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection の改善のための処置が追加されました

* 子プロセスの作成が Adobe Reader でブロックされる
* ランムウェアに対する高度な保護の使用
* すべてのプロセスOfficeプロセスを作成するのをブロックする
* アプリケーションがOfficeコンテンツを作成できないのをブロックする
* ダウンロードされた実行可能ファイルのコンテンツを、JavaScript または VBScript で起動できないのをブロックする
* 文書化されている可能性のあるスクリプトの実行をブロックする
* メール クライアントと Web メールから実行可能ファイルのコンテンツをブロックする
* 通信Office アプリケーションが子プロセスを作成するのをブロックする
* USB から実行される、信頼されていないプロセスや署名されていないプロセスをブロックする
* WMI イベント サブスクリプションによる永続性のブロック
* アプリケーションOffice他のプロセスにコードを挿入するのをブロックする
* 実行可能ファイルの実行を、提案、年齢、または信頼できるリストの条件に満たしていない場合に実行できないようにする
* PSExec コマンドと WMI コマンドからのプロセス作成をブロックする
* Windows ローカル セキュリティ機関サブシステムからの資格情報のステーリングをブロックする (lsass.exe)
* [次のマクロからの Win32 API 呼びOfficeブロックする

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>ID セキュア スコアおよび Graph API との互換性の問題

Microsoft セキュア スコアの最新のリリースでは、強化されたスコアリング モデルがリリースされました。 これらの変更により、セキュリティ状態をより柔軟かつ、より的なものに表示できます。 ただし、これらの更新は、Microsoft セキュア スコアを ID セキュア スコアおよび Graph API と一時的に互換性がもれていました。

時には、ID セキュア スコアと Graph API では新しいスコア モデルが導入されます。 それまで、Microsoft セキュア スコア、ID セキュア スコア、Graph API によって報告されたスコアの違いがユーザーに表示されます。 ご意図的な変更に対するものを取り上もっており、これらのエクスペリエンスの将来的な互換性を確保する取り上が取り上がりました。

## <a name="updated-improvement-actions"></a>改善のための処置の更新

- Azure Active Directory の改善のための処置を追加した
- Azure Advanced Threat Protection の改善のための処置を追加しました
- Microsoft Defender ATP [脅威の脆弱性&のセキュリティに関する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 推奨事項
    - TVM が提供するリリースされたセキュリティの推奨事項をすべて入手できるようになりました

## <a name="updated-interface-and-functionality"></a>更新されたインターフェイス

* CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示
* スコアを追跡して評価するための新しい方法
* スコアの連合の追跡と理解の向上
* 改善のための処置のフィルタリング、タグ付け、検索、グループ化
* スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する
* その他多数。

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、[Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿してお知らせください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [Microsoft セキュア スコアの履歴と目標への対する満たす](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
