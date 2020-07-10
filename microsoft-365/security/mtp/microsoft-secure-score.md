---
title: Microsoft セキュア スコア
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、どのようにセキュリティ体制を改善するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
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
ms.openlocfilehash: 212cefebfa3b4954f30d114419f82a5862e98a4f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094800"
---
# <a name="microsoft-secure-score"></a>Microsoft セキュア スコア

Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。 この点については https://security.microsoft.com/securescore 、「 [Microsoft 365 セキュリティセンター](overview-security-center.md)」を参照してください。

セキュリティで保護されたスコアの推奨事項に従うことで、組織を脅威から保護することができます。 Microsoft 365 セキュリティ センターの集中管理されたダッシュボードから、組織の Microsoft 365 ID、データ、アプリ、デバイス、インフラストラクチャのセキュリティを監視し、操作することができます。

セキュア スコアは、次のような方法で組織の役に立ちます。  

* 組織のセキュリティ体制の現在の状態について報告します。
* 検出可能性、可視性、ガイダンス、制御機能を提供して、セキュリティ体制を改善します。  
* ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。

指標と傾向の堅牢な視覚化、他の Microsoft 製品との統合、類似組織とのスコア比較などを、組織で利用することができます。 スコアは、サードパーティのソリューションが推奨アクションに対応した場合も反映されます。

![セキュリティで保護されたスコアホームページ](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>メカニズム

推奨されるセキュリティ機能の構成、セキュリティ関連タスクの実行、またはサードパーティ製のアプリケーションまたはソフトウェアを使用した改善アクションへの対処、または別の軽減対策を行うためのポイントが提供されています。 改善のための処置の中には、完全に完了したときにのみポイントが与えられるものがあります。また、一部のデバイスやユーザーにより完了された場合に、ポイントの一部が加えられるものもあります。 改善アクションのいずれかを実行できない、または適用したくない場合は、リスクを受け入れるか、リスクを軽減することを選択できます。

ライセンスに関係なく、考えられるすべての改善策を紹介するため、セキュリティのベスト プラクティスを理解し、スコアを向上させることができます。 絶対的なセキュリティ体制がセキュア スコアによって示されます。これは、組織が所有する製品ライセンスに関係なく常に同じです。 セキュリティは使いやすさとバランスが取れている必要があり、すべての推奨事項がご使用の環境に適しているわけではないことを覚えておいてください。

スコアはリアルタイムで更新され、視覚エフェクト ページと改善のための処置 ページに表示された情報を反映します。 またセキュア スコアは毎日同期を行い、各アクションで達成されたポイントに関するシステム データを受信します。

### <a name="key-scenarios"></a>重要なシナリオ

- [現在のスコアを確認する](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [自分のスコアを組織と同じように比較する](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [改善アクションを表示し、アクションプランを決定する](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [調査または実装のための作業フローの開始](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Microsoft 365 セキュリティセンターと ServiceNow 統合](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>改善のための処置のスコア

各改善アクションには、10ポイント以下の価値があります。 多くの場合、スコアはバイナリ方式で獲得されます。新しいポリシーを作成したり、特定の設定を有効にしたりするなど、改善のための処置を実装すると、ポイントの 100% が得られます。 その他の改善のための処置では、ポイントは構成全体に対するパーセンテージに応じて与えられます。 たとえば、強化アクションによって、多要素認証を使用するすべてのユーザーを保護することにより、すべて100のユーザーを保護することによって10ポイント獲得した場合に、保護されているユーザーの合計数が50の場合は、5ポイント (50 保護/100 合計 * 10 最大 pts = 5 ポイント部分スコア) になります。

### <a name="products-included-in-secure-score"></a>セキュア スコアに含まれる製品

現在、Microsoft 365 (Exchange Online を含む)、Azure AD、Microsoft Defender ATP、Azure ATP、および Cloud App Security に関する推奨事項があります。 その他のセキュリティ製品の推奨事項は近日リリース予定です。 推奨事項は、各製品に関連付けられているすべての攻撃対象を網羅するわけではありませんが、適切な基準になります。 また、強化された機能をサードパーティの対象としてマークしたり、別の軽減対策にマークしたりすることもできます。

### <a name="security-defaults"></a>セキュリティの既定値

Microsoft のセキュリティで保護されたスコア[では、Azure Active Directory のセキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートするように改善アクションが更新されているため、一般的な攻撃に対して構成済みのセキュリティ設定を使用して組織を保護することが容易になります

[セキュリティの既定] をオンにすると、次の強化されたアクションについて完全なポイントが付与されます。

- すべてのユーザーが、セキュリティで保護されたアクセスに対して多要素認証を完了できるようにする (9 ポイント)
- 管理役割に MFA を必要とする (10 ポイント)
- 従来の認証をブロックするポリシーを有効にする (7 ポイント)

>[!IMPORTANT]
>セキュリティの既定値には、「サインインリスクポリシー」と「ユーザーリスクポリシー」の強化アクションに似たセキュリティを提供するセキュリティ機能が含まれます。 これらのポリシーをセキュリティの既定の設定の上で設定する代わりに、それぞれの状態を "代替対策によって解決されました" に更新することをお勧めします。

## <a name="required-permissions"></a>必要なアクセス許可

Microsoft セキュア スコアにアクセスするためのアクセス許可を付与するには、Azure Active Directory で次のいずれかの役割が割り当てられている必要があります。

### <a name="read-and-write-roles"></a>読み取りと書き込みの役割

読み取りと書き込みアクセス許可があれば、変更を加えたり、セキュア スコアを直接操作したりできます。 他のユーザーに読み取り専用アクセス権を割り当てることもできます。

* グローバル管理者
* セキュリティ管理者
* Exchange 管理者
* SharePoint 管理者
* アカウント管理者

### <a name="read-only-roles"></a>読み取り専用の役割

読み取り専用アクセス許可があっても、改善のための処置のステータスやメモの編集、スコア ゾーンの編集、カスタム比較の編集を行うことはできません。

* ヘルプデスク管理者
* ユーザー管理者
* サービス管理者
* セキュリティ閲覧者
* セキュリティ オペレーター
* グローバル閲覧者

## <a name="risk-awareness"></a>リスク認識

Microsoft Secure Score は、システム構成、ユーザーの行動、およびその他のセキュリティ関連の測定値に基づいて、セキュリティの状況を示す数値の概要です。システムまたはデータが侵害される可能性の絶対的な測定値ではありません。 むしろ、それは Microsoft 環境にセキュリティ制御を適用した範囲を表します。これは、侵害のリスクを相殺するのに役立ちます。 オンライン サービスをセキュリティ侵害から完全に保護することはできません。いかなる仕方でも、セキュア スコアをセキュリティ侵害に対する保証として解釈するべきではありません。

## <a name="whats-new"></a>新機能 

Microsoft のセキュリティの評価をより良いものにするには、いくつかの変更を行いました。 予定されている変更の詳細については、「 [Microsoft Secure Score の内容](microsoft-secure-score-whats-coming.md)」を参照してください。

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Id のセキュリティで保護されたスコアとグラフ API の非互換性

Microsoft Secure Score の最近のリリースでは、向上したスコアリングモデルがリリースされました。 これらの変更により、より柔軟かつ正確にセキュリティ状況を表示することができます。 しかし、これらの更新プログラムにより、Microsoft セキュリティスコアが Id のセキュリティで保護されたスコアと Graph API とは一時的に互換性がなくなりました。

時間では、Id のセキュリティスコアと Graph API が新しいスコアリングモデルを採用します。 その後、Microsoft のセキュリティで保護されたスコア、Id のセキュリティで保護されたスコア、Graph API によって報告されたスコアの違いがわかります。 ご不便をかけて申し訳ございません。今後、このようなエクスペリエンスの互換性を確保するために取り組んでいます。

### <a name="updated-improvement-actions"></a>更新された改善アクション

- Azure Active Directory の改善アクションを追加しました
- Azure Advanced Threat Protection の向上アクションを追加しました
- Microsoft Defender ATP の[脅威 & 脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)のセキュリティに関する推奨事項のサポート
    - リリースされた TVM で提供されるすべてのセキュリティの推奨事項を使用できるようになりました。

### <a name="updated-interface-and-functionality"></a>更新されたインターフェイスと機能

* CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示
* スコアを追跡して評価するための新しい方法
* スコア回帰の追跡と理解の向上
* 改善のための処置のフィルタリング、タグ付け、検索、グループ化
* スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する
* その他多数。

### <a name="june-2020"></a>2020 年 6 月

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection の改善アクションを削除しました

* Attack Surface Reduction ルールを有効にする

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection の改善アクションが追加されました

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

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、[Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿してお知らせください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [セキュリティ体制の可視性を獲得する](microsoft-secure-score-improvement-actions.md)
- [Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
