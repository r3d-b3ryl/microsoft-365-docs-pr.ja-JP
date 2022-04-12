---
title: 動作ブロックと封じ込め
description: Microsoft Defender for Endpointで動作のブロック機能と包含機能について説明します
keywords: Microsoft Defender for Endpoint、ブロック モードでのEDR、パッシブ モードのブロック
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.localizationpriority: medium
ms.custom:
- next-gen
- edr
- admindeeplinkDEFENDER
ms.collection: m365-security-compliance
ms.technology: mde
ms.openlocfilehash: 1f598fd1463b6e08c73d7db9ac6d1540a51d6841
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790616"
---
# <a name="behavioral-blocking-and-containment"></a>動作ブロックと封じ込め

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>概要

現在の脅威の状況は [、ファイルレス マルウェア](/windows/security/threat-protection/intelligence/fileless-threats) によってオーバーランされ、従来のソリューションよりも速く変化する非常に多形の脅威と、侵害されたデバイスで敵対者が見つけるものに適応する人間が操作する攻撃によって生きています。 従来のセキュリティ ソリューションでは、このような攻撃を止めるには十分ではありません。[Defender for Endpoint](/windows/security) に含まれる人工知能 (AI) とデバイス ラーニング (ML) に対応した機能 (動作ブロックや包含など) が必要です。

動作ブロック機能とコンテインメント機能は、脅威が実行を開始した場合でも、その動作とプロセス ツリーに基づいて、脅威を特定して停止するのに役立ちます。 次世代の保護、EDR、Defender for Endpoint のコンポーネントと機能は、動作ブロック機能と包含機能で連携します。

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="Microsoft Defender ATP ポータルでの動作のブロックと包含" lightbox="images/mdatp-next-gen-EDR-behavblockcontain.png":::

動作ブロック機能とコンテインメント機能は、Defender for Endpoint の複数のコンポーネントと機能と連携して、攻撃を直ちに停止し、攻撃の進行を防ぎます。

- [次世代の保護](microsoft-defender-antivirus-in-windows-10.md) (Microsoft Defender ウイルス対策を含む) は、動作を分析して脅威を検出し、実行を開始した脅威を停止できます。

- [エンドポイントの検出と応答](overview-endpoint-detection-response.md) (EDR) は、ネットワーク、デバイス、カーネルの動作全体でセキュリティ信号を受信します。 脅威が検出されると、アラートが作成されます。 同じ種類の複数のアラートがインシデントに集計されるため、セキュリティ運用チームは調査と対応が容易になります。

- [Defender for Endpoint](overview-endpoint-detection-response.md) には、EDRを介して受信したネットワーク、エンドポイント、カーネルの動作信号に加えて、ID、電子メール、データ、アプリにわたるさまざまな光学機能があります。 [Microsoft 365 Defender](../defender/microsoft-365-defender.md)のコンポーネントである Defender for Endpoint は、これらの信号を処理して関連付け、検出アラートを発生させ、インシデント内の関連するアラートを接続します。

これらの機能を使用すると、実行を開始した場合でも、より多くの脅威を防止またはブロックできます。 疑わしい動作が検出されるたびに、脅威が含まれ、アラートが作成され、脅威が追跡で停止されます。

次の図は、動作ブロック機能と包含機能によってトリガーされたアラートの例を示しています。

:::image type="content" source="images/blocked-behav-alert.png" alt-text="動作のブロックと包含によるアラートを含む [アラート] ページ" lightbox="images/blocked-behav-alert.png":::

## <a name="components-of-behavioral-blocking-and-containment"></a>動作ブロックとコンテインメントのコンポーネント

- **クライアント上のポリシー主導の [攻撃面の縮小ルール](attack-surface-reduction.md)** 定義済みの一般的な攻撃動作は、攻撃面の縮小ルールに従って実行できなくなります。 このような動作を実行しようとすると、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderに情報</a>アラートとして表示されます。 攻撃対象の縮小ルールは既定では有効になっていません。[Microsoft 365 Defender ポータル](/microsoft-365/security/defender/microsoft-365-defender)でポリシーを構成します。

- **[クライアントの動作のブロック](client-behavioral-blocking.md)** エンドポイント上の脅威は機械学習を通じて検出され、ブロックされ、自動的に修復されます。 (クライアントの動作ブロックは既定で有効になっています。

- **[フィードバック ループブロック](feedback-loop-blocking.md)** (迅速な保護とも呼ばれます) 脅威の検出は、行動インテリジェンスを通じて観察されます。 脅威は停止され、他のエンドポイントで実行されなくなります。 (フィードバック ループブロックは既定で有効になっています。

- **[ブロック モードでのエンドポイントの検出と応答 (EDR)](edr-in-block-mode.md)** 侵害後の保護によって観察される悪意のある成果物または動作はブロックされ、含まれます。 ブロック モードのEDRは、Microsoft Defender ウイルス対策がプライマリウイルス対策ソリューションでない場合でも機能します。 (ブロック モードのEDRは既定では有効になっていません。Microsoft 365 Defenderで有効にします)。

Microsoft は脅威の保護機能と機能を引き続き向上させ続けているので、行動のブロックと包含の分野でさらに多くのことを期待してください。 現在の計画と展開を確認するには、[Microsoft 365ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を参照してください。

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>動作ブロックとコンテインメントの動作の例

動作のブロック機能と包含機能により、次のような攻撃者の手法がブロックされています。

- LSASS からの資格情報ダンプ
- クロスプロセスインジェクション
- プロセスのくり抜き
- ユーザー アカウント制御のバイパス
- ウイルス対策の改ざん (無効にしたり、マルウェアを除外として追加したりするなど)
- コマンドとコントロール (C&C) に連絡してペイロードをダウンロードする
- コイン マイニング
- ブート レコードの変更
- Pass-the-hash attacks
- ルート証明書のインストール
- さまざまな脆弱性に対する悪用の試み

動作のブロックと包含の実際の 2 つの例を次に示します。

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>例 1: 100 組織に対する資格情報盗難攻撃

「 [不可解な脅威の熱い追求:AI 主導の行動ベースのブロックは、そのトラックでの攻撃を停止します](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)。世界中の 100 の組織に対する資格情報の盗難攻撃は、行動ブロックと封じ込めの機能によって停止されました。 スピア フィッシングメール メッセージには、対象となる組織に対して、おびえのドキュメントを含むメール メッセージが送信されました。 受信者が添付ファイルを開いた場合、関連するリモート ドキュメントはユーザーのデバイスでコードを実行し、Lokibot マルウェアを読み込むことができました。これにより、資格情報が盗まれ、盗まれたデータが流出し、コマンドアンドコントロール サーバーからの詳細な指示が待たされます。

Defender for Endpoint の動作ベースのデバイスラーニング モデルは、攻撃チェーンの 2 つの時点で攻撃者の手法をキャッチして停止しました。

- 最初の保護レイヤーは、悪用動作を検出しました。 クラウドのデバイスラーニング分類子は、脅威を正しく識別し、攻撃をブロックするようにクライアント デバイスに直ちに指示しました。
- 2 番目の保護レイヤーは、攻撃が最初のレイヤーを過ぎた場合の停止、プロセスのくぼみの検出、そのプロセスの停止、対応するファイル (Lokibot など) の削除に役立ちました。

攻撃の検出と停止中に、"初期アクセス アラート" などのアラートがトリガーされ[、Microsoft 365 Defender ポータル](/microsoft-365/security/defender/microsoft-365-defender)に表示されました。

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Microsoft 365 Defender ポータルの初期アクセス アラート" lightbox="images/behavblockcontain-initialaccessalert.png":::

この例では、クラウド内の動作ベースのデバイスラーニング モデルが、実行を開始した後でも、攻撃に対する保護の新しいレイヤーを追加する方法を示します。

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>例 2: NTLM リレー - Malware Variant

最近のブログ投稿「 [動作のブロックと包含: 光学を保護に変換する](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)」で説明したように、2020 年 1 月、Defender for Endpoint は組織内のデバイスで特権エスカレーション アクティビティを検出しました。 "NTLM リレーを使用した特権エスカレーションの可能性" というアラートがトリガーされました。

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="Malwarey Potato マルウェアに対する NTLM アラート" lightbox="images/NTLMalertjuicypotato.png":::

脅威はマルウェアであることが判明しました。これは、攻撃者がデバイスの特権エスカレーションを取得するために使用される、悪名高い Hacking Tool の新しい、未確認のバリエーションです。

アラートがトリガーされた数分後に、ファイルが分析され、悪意のあるファイルであることが確認されました。 次の図に示すように、プロセスは停止され、ブロックされました。

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="ブロックされたアーティファクト"  lightbox="images/Artifactblockedjuicypotato.png":::

アーティファクトがブロックされてから数分後、同じデバイスで同じファイルの複数のインスタンスがブロックされ、より多くの攻撃者やその他のマルウェアがデバイスにデプロイされるのを防ぎます。

この例では、動作のブロック機能と包含機能を使用すると、脅威が自動的に検出、包含、ブロックされることを示します。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)

## <a name="next-steps"></a>次の手順

- [Defender for Endpoint の詳細を確認する](overview-endpoint-detection-response.md)

- [攻撃対象の縮小ルールを構成する](attack-surface-reduction.md)

- [ブロック モードでEDRを有効にする](edr-in-block-mode.md)

- [最近のグローバル脅威アクティビティを表示する](https://www.microsoft.com/wdsi/threats)

- [Microsoft 365 Defenderの概要を確認する](../defender/microsoft-365-defender.md)
