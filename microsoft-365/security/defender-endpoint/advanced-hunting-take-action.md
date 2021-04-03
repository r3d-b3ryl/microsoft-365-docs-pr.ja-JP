---
title: Microsoft Threat Protection で高度な検索クエリ結果に対してアクションを実行する
description: 高度な検索クエリ結果の脅威と影響を受けるアセットにすばやく対処する
keywords: 高度な狩猟、脅威狩り、サイバー脅威の狩猟、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、回避タイムアウト、コマンド ライン、プロセス ID
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: d1dbe226cef5e94b36fcd6c35b839118b200f85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500533"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>高度な検索クエリの結果に対してアクションを実行する

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

強力で包括的なアクション オプションを使用して、高度な狩[](advanced-hunting-overview.md)猟で見つけた脅威を迅速に含め、または侵害された資産に対処できます。 これらのオプションを使用すると、次の機能を使用できます。

- デバイスでさまざまなアクションを実行する
- 検疫ファイル

## <a name="required-permissions"></a>必要なアクセス許可

高度な検索を通じてアクションを実行するには、デバイスに修復アクションを送信するためのアクセス許可を持つ Defender for Endpoint の役割 [が必要です](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options)。 アクションを実行できない場合は、次のアクセス許可を取得する方法について、グローバル管理者に問い合わせてください。

*脅威と脆弱性管理>アクティブな修復アクション - 修復処理*

## <a name="take-various-actions-on-devices"></a>デバイスでさまざまなアクションを実行する

クエリ結果の列で識別されるデバイスに対して、次 `DeviceId` のアクションを実行できます。

- 影響を受けるデバイスを分離して、感染を含むか、攻撃が横方向に移動しなかっ
- 調査パッケージを収集して、より多くの調査情報を取得する
- ウイルス対策スキャンを実行して、最新のセキュリティ インテリジェンス更新プログラムを使用して脅威を検索および削除する
- 自動調査を開始して、デバイスおよび他の影響を受ける可能性のあるデバイス上の脅威を確認および修復する
- アプリの実行を Microsoft が署名した実行可能ファイルにのみ制限し、マルウェアや他の信頼されていない実行可能ファイルによる後続の脅威アクティビティを防止する

Defender for Endpoint を通じてこれらの応答アクションがどのように実行されるのかについて詳しくは、デバイス [での応答アクションに関するページをご覧ください](respond-machine-alerts.md)。

## <a name="quarantine-files"></a>検疫ファイル

ファイルに検疫アクション *を* 展開すると、ファイルが検出された場合に自動的に検疫されます。 このアクションを選択すると、次の列から選択して、検疫するクエリ結果内のファイルを識別できます。

- `SHA1` — 最も高度な検索テーブルでは、記録されたアクションの影響を受けたファイルの SHA-1 です。 たとえば、ファイルがコピーされた場合、これはコピーされたファイルです。
- `InitiatingProcessSHA1` — 最も高度な検索テーブルでは、記録されたアクションの開始を担当するファイルです。 たとえば、子プロセスが起動された場合、これは親プロセスになります。 
- `SHA256` — これは、列で識別されるファイルに相当する SHA-256 `SHA1` です。
- `InitiatingProcessSHA256` — これは、列で識別されるファイルに相当する SHA-256 `InitiatingProcessSHA1` です。

検疫アクションの実行方法とファイルの復元方法の詳細については、「ファイルに対する応答アクション」 [を参照してください](respond-file-alerts.md)。

>[!NOTE]
>ファイルを検索して検疫するには、クエリ結果に値を `DeviceId` デバイス識別子として含める必要があります。  

## <a name="take-action"></a>アクションを行う

説明されているアクションのいずれかを実行するには、クエリ結果で 1 つ以上のレコードを選択し、[アクションの実行] **を選択します**。 ウィザードを使用すると、優先するアクションを選択して送信するプロセスを案内します。

![選択したレコードの画像(レコードを検査するパネル付き)](images/ah-take-actions.png)

## <a name="review-actions-taken"></a>実行されたアクションを確認する

各アクションは、アクション センターの [アクション センターの履歴 ] ( [ security.microsoft.com/action-center/history ] の下に  >  [個別に記録されます](https://security.microsoft.com/action-center/history)。 アクション センターに移動して、各アクションの状態を確認します。
 
## <a name="related-topics"></a>関連項目

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](overview-custom-detections.md)
