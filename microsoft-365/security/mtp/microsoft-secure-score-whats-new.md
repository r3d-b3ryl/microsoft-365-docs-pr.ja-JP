---
title: Microsoft セキュリティスコアの新機能
description: Microsoft 365 セキュリティセンターの Microsoft セキュリティスコアに対して発生した新しい変更点について説明します。
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
ms.openlocfilehash: e31389705ddd8de4854a3477012d7fa90b78c7ee
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866897"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft セキュリティスコアの新機能

Microsoft のセキュリティの評価をより良いものにするには、いくつかの変更を行いました。 予定されている変更の詳細については、「 [Microsoft Secure Score の内容](microsoft-secure-score-whats-coming.md)」を参照してください。

## <a name="july-2020"></a>2020 年7 月

### <a name="adding-improvement-actions-for-azure-advanced-threat-protection"></a>Azure Advanced Threat Protection の改善アクションを追加する

- 危険性のある横移動パス
- 安全でないアカウントの属性
- Active Directory 信頼でセキュリティ機能を有効にする
- セキュリティ保護のない SID 履歴属性をエンティティから削除する

## <a name="june-2020"></a>2020 年 6 月

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection の改善アクションを削除しました

* Attack Surface Reduction ルールを有効にする

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection の改善アクションが追加されました

* Adobe Reader が子プロセスを作成するのをブロックする
* ランサムウェアに対する高度な保護の使用
* すべての Office アプリケーションで子プロセスを作成することを禁止する
* Office アプリケーションで実行可能なコンテンツを作成することを禁止する
* JavaScript または VBScript がダウンロードされた実行可能コンテンツを起動するのをブロックする
* 難読化する可能性のあるスクリプトの実行をブロックする
* 電子メールクライアントおよび webmail からの実行可能ファイルのコンテンツをブロックする
* Office コミュニケーションアプリケーションによる子プロセスの作成を禁止する
* USB から実行される信頼できないおよび署名されていないプロセスをブロックする
* WMI イベントサブスクリプション経由の永続化をブロックする
* Office アプリケーションが他のプロセスにコードを挿入するのをブロックする
* 実行可能ファイルが、流行、年齢、または信頼できるリストの条件を満たしていない限り、実行を禁止する
* PSExec および WMI コマンドからのプロセス作成をブロックする
* Windows ローカルセキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)
* Office マクロからの Win32 API 呼び出しをブロックする

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Id のセキュリティで保護されたスコアとグラフ API の非互換性

Microsoft Secure Score の最近のリリースでは、向上したスコアリングモデルがリリースされました。 これらの変更により、より柔軟かつ正確にセキュリティ状況を表示することができます。 しかし、これらの更新プログラムにより、Microsoft セキュリティスコアが Id のセキュリティで保護されたスコアと Graph API とは一時的に互換性がなくなりました。

時間では、Id のセキュリティスコアと Graph API が新しいスコアリングモデルを採用します。 その後、Microsoft のセキュリティで保護されたスコア、Id のセキュリティで保護されたスコア、Graph API によって報告されたスコアの違いがわかります。 ご不便をかけて申し訳ございません。今後、このようなエクスペリエンスの互換性を確保するために取り組んでいます。

## <a name="updated-improvement-actions"></a>更新された改善アクション

- Azure Active Directory の改善アクションを追加しました
- Azure Advanced Threat Protection の向上アクションを追加しました
- Microsoft Defender ATP の [脅威 & 脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) のセキュリティに関する推奨事項のサポート
    - リリースされた TVM で提供されるすべてのセキュリティの推奨事項を使用できるようになりました。

## <a name="updated-interface-and-functionality"></a>更新されたインターフェイスと機能

* CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示
* スコアを追跡して評価するための新しい方法
* スコア回帰の追跡と理解の向上
* 改善のための処置のフィルタリング、タグ付け、検索、グループ化
* スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する
* その他多数。

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティ」に投稿してお知らせください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
