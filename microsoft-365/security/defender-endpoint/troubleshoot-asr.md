---
title: 攻撃表面の縮小ルールに関する問題のトラブルシューティング
description: Microsoft Defender for Endpoint の攻撃表面縮小ルールに関する問題のトラブルシューティングを行うリソースとサンプル コード。
keywords: トラブルシューティング、エラー、修正、Windows Defender 例、asr、ルール、ヒップ、トラブルシューティング、監査、除外、誤検知、破損、ブロック、エンドポイント用 Microsoft Defender、Microsoft Defender Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: d090c82e8c76da8f2e19dc9189006fdea3d6990d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066811"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>攻撃表面の縮小ルールのトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


攻撃表面の [縮小ルールを使用すると、](attack-surface-reduction.md) 次のような問題が発生する可能性があります。

- ルールは、ファイル、プロセス、または実行すべきではない他のアクションをブロックします (誤検知)

- ルールが説明に従って機能しないか、ファイルまたはプロセスをブロックしない (false 負の値)

これらの問題のトラブルシューティングには、次の 4 つの手順があります。

1. [前提条件の確認](#confirm-prerequisites)

2. [監査モードを使用してルールをテストする](#use-audit-mode-to-test-the-rule)

3. [指定したルールの除外を追加](#add-exclusions-for-a-false-positive) する (誤検知の場合)

4. [サポート ログの送信](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>前提条件の確認

攻撃表面の縮小ルールは、次の条件を持つデバイスでのみ機能します。

- エンドポイントは、Windows 10 Enterprise バージョン 1709 (Fall Creators Update とも呼ばれる) を実行しています。

- エンドポイントは、Microsoft Defender Antivirus を唯一のウイルス対策保護アプリとして使用しています。 [他のウイルス対策アプリを使用すると、Microsoft Defender AV がそれ自体を無効にします](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。

- [リアルタイム保護が](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) 有効になっています。

- 監査モードが有効になっていません。 「攻撃表面の縮小ルールを有効にする」の説明に従って、グループ ポリシーを使用してルールを無効 **(値**: **0)**[に設定します](enable-attack-surface-reduction.md)。

これらの前提条件が満たされている場合は、次の手順に進み、監査モードでルールをテストします。

## <a name="use-audit-mode-to-test-the-rule"></a>監査モードを使用してルールをテストする

demo.wd.microsoft.com の [Windows Defender](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) テスト グラウンド Web サイトにアクセスして、攻撃表面の縮小ルールが一般的にデバイス上の事前構成されたシナリオとプロセスで機能しているか、または監査モードを使用して、レポートのルールのみを有効にできます。

「デモ ツールを使用 [する」の](evaluate-attack-surface-reduction.md) 手順に従って、問題が発生している特定のルールをテストするために攻撃表面の縮小ルールがどのように機能するのか確認します。

1. テストする特定のルールの監査モードを有効にします。 グループ ポリシーを使用してルールを **監査モード** (値: **2)** に設定します 。「攻撃表面の縮小ルールを有効にする [」の説明に従います](enable-attack-surface-reduction.md)。 監査モードでは、ルールはファイルまたはプロセスを報告できますが、実行は許可されます。

2. 問題の原因となっているアクティビティを実行します (たとえば、ブロックする必要があるが許可されているファイルまたはプロセスを開く、または実行する)。

3. [ルールが [有効] に](attack-surface-reduction.md) 設定されている場合、ルールがファイルまたはプロセスをブロックした可能性がある場合は、攻撃表面縮小ルールイベント ログを確認 **します**。

ルールがブロックするファイルまたはプロセスをブロックしない場合は、まず監査モードが有効になっているか確認します。

監査モードは、別の機能のテスト、または自動化された PowerShell スクリプトによって有効になっている可能性があります。テストが完了した後は無効になっていない可能性があります。

デモ ツールと監査モードでルールをテストし、攻撃表面の縮小ルールが構成済みのシナリオで動作しているが、ルールが期待通り動作しない場合は、状況に基づいて次のいずれかのセクションに進みます。

1. 攻撃表面の縮小ルールがブロックしないブロック (誤検知とも呼ばれる) をブロックしている場合は、最初に攻撃表面の縮小ルールの除外を [追加できます](#add-exclusions-for-a-false-positive)。

2. 攻撃表面の縮小ルールがブロックする必要があるもの (偽陰性とも呼ばれる) をブロックしない場合は、直ちに最後の手順に進み、診断データを収集し、問題を提出[することができます。](#collect-diagnostic-data-for-file-submissions)

## <a name="add-exclusions-for-a-false-positive"></a>誤検知の除外を追加する

攻撃表面の縮小ルールがブロックしてはならないものをブロックしている場合 (誤検知とも呼ばれる)、除外を追加して、攻撃表面の縮小ルールが除外されたファイルまたはフォルダーを評価してはならないことを防止できます。

除外を追加するには、「攻撃表面の [縮小をカスタマイズする」を参照してください](customize-attack-surface-reduction.md)。

>[!IMPORTANT]
>除外する個々のファイルとフォルダーを指定できますが、個々のルールを指定することはできません。
>つまり、除外されるファイルまたはフォルダーは、すべての ASR ルールから除外されます。

## <a name="report-a-false-positive-or-false-negative"></a>誤検知または偽陰性を報告する

ネットワーク保護用 [Windows Defender偽](https://www.microsoft.com/wdsi/filesubmission) 陰性または誤検知を報告するには、[セキュリティ インテリジェンス] Web ベースの送信フォームを使用します。 Windows E5 サブスクリプションを使用すると、関連付けられたアラート [へのリンクを提供できます](alerts-queue.md)。

## <a name="collect-diagnostic-data-for-file-submissions"></a>ファイル提出の診断データを収集する

攻撃表面の縮小ルールに関する問題を報告する場合は、Microsoft のサポートチームとエンジニアリング チームが問題のトラブルシューティングに役立つ診断データを収集して提出する必要があります。

1. 管理者特権のコマンド プロンプトを開き、次のディレクトリWindows Defenderします。

   ```console
   cd "c:\program files\windows defender"
   ```

2. 次のコマンドを実行して、診断ログを生成します。

   ```console
   mpcmdrun -getfiles
   ```

3. 既定では、 に保存されます `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 。 提出フォームにファイルを添付します。

## <a name="related-articles"></a>関連記事

- [攻撃面の減少ルール](attack-surface-reduction.md)

- [攻撃表面の縮小ルールを有効にする](enable-attack-surface-reduction.md)

- [攻撃表面の縮小ルールを評価する](evaluate-attack-surface-reduction.md)
