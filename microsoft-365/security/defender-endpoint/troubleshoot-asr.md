---
title: 攻撃面の縮小ルールに関する問題のトラブルシューティング
description: Microsoft Defender for Endpointの攻撃表面縮小ルールに関する問題のトラブルシューティングを行うリソースとサンプル コード。
keywords: トラブルシューティング, エラー, 修正, Windows Defender 例, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: c503c3ed4cfea4ed0645cf18a9c9bf4ebe4a5ade
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807250"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>攻撃対象の縮小ルールのトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

[攻撃表面の縮小ルール](attack-surface-reduction.md)を使用すると、次のような問題が発生する可能性があります。

- ルールは、ファイルをブロック、処理、または実行する必要がない他のアクションを実行します (誤検知)
- ルールは説明どおりに機能しないか、必要なファイルまたはプロセスをブロックしません (false negative)

これらの問題のトラブルシューティングには、次の 4 つの手順があります。

1. [前提条件を確認する](#confirm-prerequisites)
2. [監査モードを使用してルールをテストする](#use-audit-mode-to-test-the-rule)
3. [指定したルールの除外を追加する](#add-exclusions-for-a-false-positive) (誤検知の場合)
4. [サポート ログを送信する](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>前提条件を確認する

攻撃表面の縮小ルールは、次の条件を持つデバイスでのみ機能します。

- エンドポイントは、バージョン 1709 (Fall Creators Update とも呼ばれます) Windows 10 Enterprise実行されています。

- エンドポイントは、唯一のウイルス対策保護アプリとしてMicrosoft Defender ウイルス対策を使用しています。 [その他のウイルス対策アプリを使用すると、Microsoft Defender ウイルス対策自体が無効](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)になります。

- [リアルタイム保護](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) が有効になっています。

- 監査モードが有効になっていません。 グループ ポリシーを使用して、ルールを **無効** (値: **0**) に設定します。「[攻撃面の縮小ルールを有効にする」](enable-attack-surface-reduction.md)の説明に従います。

これらの前提条件がすべて満たされている場合は、次の手順に進み、監査モードでルールをテストします。

## <a name="use-audit-mode-to-test-the-rule"></a>監査モードを使用してルールをテストする

[demo.wd.microsoft.com のWindows Defender](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) テスト グラウンド Web サイトにアクセスして、攻撃表面の縮小ルールが一般にデバイス上で事前に構成されたシナリオとプロセスに対して機能していることを確認したり、監査モードを使用してレポートのみのルールを有効にしたりできます。

> [!NOTE]
> demo.wd.microsoft.com の Defender for Endpoint デモ サイトは推奨されません。今後削除される予定です。

デモ ツールの使用に関するページの手順に従って、問題が発生している特定の [ルールをテストするために、攻撃表面の縮小ルールがどのように機能するかを確認します](evaluate-attack-surface-reduction.md) 。

1. テストする特定のルールの監査モードを有効にします。 グループ ポリシーを使用して、ルールを **監査モード** (値: **2**) に設定します。「[攻撃面の縮小ルールを有効にする」](enable-attack-surface-reduction.md)の説明に従います。 監査モードでは、ルールでファイルまたはプロセスをレポートできますが、実行は許可されます。

2. 問題の原因となっているアクティビティを実行します (たとえば、ブロックする必要があるが許可されているファイルまたはプロセスを開いたり実行したりします)。

3. [攻撃対象の縮小ルール イベント ログを確認](attack-surface-reduction.md) して、ルールが **[有効]** に設定されている場合に、ルールがファイルまたはプロセスをブロックしたかどうかを確認します。

ルールがブロックする必要があるファイルまたはプロセスをブロックしていない場合は、最初に監査モードが有効になっているかどうかを確認します。

監査モードは、別の機能のテストまたは自動 PowerShell スクリプトによって有効になっており、テストが完了した後は無効になっていない可能性があります。

デモ ツールと監査モードを使用してルールをテストし、攻撃表面の縮小ルールが事前構成されたシナリオで動作しているが、ルールが想定どおりに機能していない場合は、状況に基づいて次のいずれかのセクションに進みます。

1. 攻撃表面の縮小ルールがブロックすべきでないものをブロックしている場合 (偽陽性とも呼ばれます)、 [最初に攻撃面の縮小ルールの除外を追加](#add-exclusions-for-a-false-positive)できます。

2. 攻撃表面の縮小ルールがブロックすべきものをブロックしていない場合 (偽陰性とも呼ばれます)、最後の手順に直ちに進み、 [診断データを収集し、問題を Microsoft に送信することができます](#collect-diagnostic-data-for-file-submissions)。

## <a name="add-exclusions-for-a-false-positive"></a>誤検知の除外を追加する

攻撃表面の縮小ルールがブロックすべきでないものをブロックしている場合 (誤検知とも呼ばれます)、除外を追加して、攻撃表面の縮小ルールが除外されたファイルまたはフォルダーを評価できないようにすることができます。

除外を追加するには、「 [攻撃面の縮小をカスタマイズ](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules)する」を参照してください。

> [!IMPORTANT]
> 除外する個々のファイルとフォルダーは指定できますが、個々のルールを指定することはできません。
> つまり、除外されたすべてのファイルまたはフォルダーは、すべての ASR ルールから除外されます。

## <a name="report-a-false-positive-or-false-negative"></a>偽陽性または偽陰性を報告する

[Windows Defender Security Intelligence Web ベースの送信フォーム](https://www.microsoft.com/wdsi/filesubmission)を使用して、ネットワーク保護の偽陰性または偽陽性を報告します。 Windows E5 サブスクリプションでは、[関連付けられているアラートへのリンクを指定](alerts-queue.md)することもできます。

## <a name="collect-diagnostic-data-for-file-submissions"></a>ファイル送信の診断データを収集する

攻撃面の縮小ルールに関する問題を報告すると、Microsoft サポートチームとエンジニアリング チームが問題のトラブルシューティングに役立つ診断データを収集して送信するように求められます。

1. 管理者特権のコマンド プロンプトを開き、Windows Defender ディレクトリに変更します。

   ```console
   cd "c:\program files\windows defender"
   ```

2. 次のコマンドを実行して診断ログを生成します。

   ```console
   mpcmdrun -getfiles
   ```

3. 既定では、.`C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 提出フォームにファイルを添付します。

## <a name="related-articles"></a>関連記事

- [攻撃面の減少ルール](attack-surface-reduction.md)
- [攻撃面の減少ルールを有効にする](enable-attack-surface-reduction.md)
- [攻撃面の減少ルールを評価する](evaluate-attack-surface-reduction.md)
