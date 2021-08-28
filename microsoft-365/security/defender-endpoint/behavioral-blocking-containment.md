---
title: 動作ブロックと封じ込め
description: Microsoft Defender for Endpoint での動作のブロックと格納機能について説明します。
keywords: Microsoft Defender for Endpoint,EDRモードでのサポート、パッシブ モードのブロック
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 7d9dad6b2f2f1b37525faf0a4a90d143650c49d1
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58570367"
---
# <a name="behavioral-blocking-and-containment"></a>動作ブロックと封じ込め

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>概要

今日の脅威の状況は、ファイルレス[](/windows/security/threat-protection/intelligence/fileless-threats)マルウェアによって過剰に実行され、土地から離れ、従来のソリューションよりも高速に変化する高度な多態性の脅威、および侵害されたデバイスで敵が見つけたものに適応する人が操作する攻撃です。 従来のセキュリティ ソリューションでは、このような攻撃を止めるには十分ではありません。Defender for Endpoint に含まれる、動作のブロックや格納などの、人工知能 (AI) とデバイス学習 (ML) のサポート機能[が必要です](/windows/security)。

動作のブロックと格納機能は、脅威の実行が開始された場合でも、その動作とプロセス ツリーに基づいて、脅威を特定して停止するのに役立ちます。 次世代の保護、EDR、Defender for Endpoint のコンポーネントと機能は、動作ブロック機能と格納機能で機能します。

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="動作のブロックと格納。":::

動作のブロックと格納機能は、Defender for Endpoint の複数のコンポーネントと機能と組み合わせ、攻撃を直ちに停止し、攻撃の進行を防止します。

- [次世代の保護](microsoft-defender-antivirus-in-windows-10.md)(Microsoft Defender ウイルス対策を含む) は、動作を分析して脅威を検出し、実行を開始した脅威を停止できます。

- [エンドポイントの検出と応答](overview-endpoint-detection-response.md)(EDR) は、ネットワーク、デバイス、カーネルの動作全体でセキュリティ信号を受信します。 脅威が検出されると、アラートが作成されます。 同じ種類の複数のアラートがインシデントに集約され、セキュリティ運用チームが調査して対応しやすくなります。

- [Defender for Endpoint](overview-endpoint-detection-response.md)には、EDR を介して受信したネットワーク、エンドポイント、カーネルの動作信号に加えて、ID、電子メール、データ、アプリにわたるさまざまな光学機能があります。 Microsoft 365 Defender [、Defender](../defender/microsoft-365-defender.md)for Endpoint のコンポーネントは、これらの信号を処理して関連付け、検出アラートを発生し、インシデントに関連するアラートを接続します。

これらの機能を使用すると、実行を開始した場合でも、より多くの脅威を防止またはブロックできます。 疑わしい動作が検出されると、脅威が含まれる、アラートが作成され、脅威は追跡で停止されます。

次の図は、動作ブロックと格納機能によってトリガーされたアラートの例を示しています。

:::image type="content" alt-text="動作のブロックと格納によるアラートの例。" source="images/blocked-behav-alert.png" lightbox="images/blocked-behav-alert.png":::

## <a name="components-of-behavioral-blocking-and-containment"></a>動作のブロックと格納のコンポーネント

- **クライアント上のポリシー駆動型攻撃 [表面の縮小ルール](attack-surface-reduction.md)** 定義済みの一般的な攻撃動作は、攻撃表面の縮小ルールに従って実行されません。 このような動作を実行しようとすると、ポータル( ) の情報Microsoft 365 Defender [https://security.microsoft.com](https://security.microsoft.com) として表示されます。 攻撃表面の縮小ルールは既定では有効になっていません。ポリシーは、Microsoft 365 Defender[ポータルで構成します](microsoft-defender-security-center.md)。

- **[クライアントの動作のブロック](client-behavioral-blocking.md)** エンドポイント上の脅威は機械学習によって検出され、ブロックされ、自動的に修復されます。 (クライアントの動作ブロックは既定で有効になっています)。

- **[フィードバック ループブロック](feedback-loop-blocking.md)** (高速保護とも呼ばれます) 脅威検出は、行動インテリジェンスを通じて観察されます。 脅威は停止され、他のエンドポイントで実行されません。 (フィードバック ループのブロックは既定で有効になっています)。

- **[ブロック モードでのエンドポイントEDR応答 (EDR)](edr-in-block-mode.md)** 侵害後の保護によって観察される悪意のあるアーティファクトや動作はブロックされ、含まれる。 EDRウイルス対策ソリューションではない場合でも、ブロック モードMicrosoft Defender ウイルス対策機能します。 (EDRモードの設定は既定では有効になっていません。既定では有効Microsoft 365 Defender)。

Microsoft は引き続き脅威保護の機能を向上させるので、行動のブロックと格納の領域でさらに多くのことを期待してください。 今計画されている計画と展開を確認するには、次のロードマップを[Microsoft 365してください](https://www.microsoft.com/microsoft-365/roadmap)。

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>動作ブロックとアクション内の格納の例

動作のブロックと封じ込め機能によって、次のような攻撃者の手法がブロックされています。

- LSASS からの資格情報のダンプ
- プロセス間の挿入
- プロセスの空洞化
- ユーザー アカウント制御のバイパス
- ウイルス対策の改ざん (無効にする、マルウェアを除外として追加するなど)
- ペイロードをダウンロードするコマンドとコントロール (C&C) への連絡
- コイン マイニング
- ブート レコードの変更
- ハッシュパス攻撃
- ルート証明書のインストール
- さまざまな脆弱性に対する悪用の試み

以下に、実際の動作ブロックとイントメントの 2 つの実際の例を示します。

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>例 1: 100 組織に対する資格情報の盗難攻撃

「AI[](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)による行動ベースのブロックは、追跡中の攻撃を停止する」で説明したように、世界中の 100 の組織に対する資格情報の盗難攻撃は、行動ブロックと格納機能によって停止されました。 ルアー ドキュメントを含むスピア フィッシングメール メッセージが、対象の組織に送信されました。 受信者が添付ファイルを開いた場合、関連するリモート ドキュメントはユーザーのデバイスでコードを実行し、Lokibot マルウェアを読み込む事ができた。これは資格情報を盗み、盗まれたデータを汚し、コマンド アンド コントロール サーバーからのさらなる指示を待った。

Defender for Endpoint の動作ベースのデバイス学習モデルは、攻撃チェーンの 2 つのポイントで攻撃者の手法をキャッチして停止しました。

- 最初の保護層が悪用の動作を検出しました。 クラウド内のデバイス学習分類子は、脅威を正しく識別し、すぐにクライアント デバイスに攻撃をブロックするように指示しました。
- 2 番目の保護層は、攻撃が最初のレイヤーを越え、プロセスの空きを検出し、そのプロセスを停止し、対応するファイル (Lokibot など) を削除した場合の停止に役立ちます。

攻撃が検出および停止されている間に、"初期アクセスアラート" などのアラートがトリガーされ、Microsoft 365 Defender[ポータルに表示されました](microsoft-defender-security-center.md)。

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="ポータルの初期アクセス通知Microsoft 365 Defenderします。":::

次の使用例は、クラウド内の動作ベースのデバイス学習モデルが、実行を開始した後でも、攻撃に対する新しい保護層を追加する方法を示しています。

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>例 2: NTLM リレー - ジューシー ポテト マルウェアバリアント

最近のブログ投稿「ビヘイビアーブロック[](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)と格納: 光学を保護に変換する」で説明したように、2020 年 1 月に Defender for Endpoint は組織内のデバイスで特権エスカレーション アクティビティを検出しました。 "NTLM リレーを使用した特権エスカレーションの可能性" というアラートがトリガーされました。

:::image type="content" alt-text="ジューシー ジャガイモ マルウェアに関する NTLM アラート。" source="images/NTLMalertjuicypotato.png" lightbox="images/NTLMalertjuicypotato.png":::

脅威はマルウェアである判明しました。これは、デバイスの特権エスカレーションを取得するために攻撃者によって使用される、ジュート ポテトと呼ばれる悪名高いハッキング ツールの新しい、前に見られないバリアントでした。

アラートがトリガーされた数分後、ファイルが分析され、悪意のあるものに確認されました。 次の図に示すように、プロセスは停止およびブロックされました。

:::image type="content" alt-text="アーティファクトがブロックされました。" source="images/Artifactblockedjuicypotato.png" lightbox="images/Artifactblockedjuicypotato.png":::

アーティファクトがブロックされた数分後、同じファイルの複数のインスタンスが同じデバイスでブロックされ、攻撃者や他のマルウェアがデバイスに展開されるのを防ぐ。

この例では、動作のブロックと封じ込め機能を使用すると、脅威が検出され、格納され、自動的にブロックされます。

## <a name="next-steps"></a>次の手順

- [Defender for Endpoint の詳細](overview-endpoint-detection-response.md)

- [攻撃表面の縮小ルールを構成する](attack-surface-reduction.md)

- [ブロック モードEDR有効にする](edr-in-block-mode.md)

- [最近のグローバル脅威アクティビティを確認する](https://www.microsoft.com/wdsi/threats)

- [アプリケーションの概要をMicrosoft 365 Defender](../defender/microsoft-365-defender.md)
