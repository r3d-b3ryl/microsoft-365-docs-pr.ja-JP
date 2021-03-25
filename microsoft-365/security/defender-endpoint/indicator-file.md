---
title: ファイルのインジケーターを作成する
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義するファイル ハッシュのインジケーターを作成します。
keywords: ファイル、ハッシュ、管理、許可、ブロック、ブロック、クリーン、悪意のある、ファイル ハッシュ、IP アドレス、URL、ドメイン
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 35a0b66a4cdc4cf39c15329eda2e0aafced79f34
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199611"
---
# <a name="create-indicators-for-files"></a>ファイルのインジケーターを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

悪意のある可能性のあるファイルやマルウェアの疑いを禁止することで、組織での攻撃の伝播をさらに防ぐことが可能です。 悪意のある可能性のあるポータブル実行可能ファイル (PE) ファイルが分かっている場合は、そのファイルをブロックできます。 この操作によって、組織内のコンピューターで読み取り、書き込み、または実行されるのを防ぐ。

ファイルのインジケーターを作成するには、次の 2 つの方法があります。
- 設定ページからインジケーターを作成する
- ファイルの詳細ページからインジケーターの追加ボタンを使用してコンテキスト インジケーターを作成する

### <a name="before-you-begin"></a>はじめに
ファイルのインジケーターを作成する前に、次の前提条件を理解することが重要です。

- この機能は、組織でウイルス対策とクラウドベースWindows Defenderが有効になっている場合に使用できます。 詳細については、「クラウド提供の保護を通じて Microsoft Defender ウイルス対策で次世代テクノロジを使用する [」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)。
- マルウェア対策クライアントのバージョンは、4.18.1901.x 以降である必要があります。
- Windows 10 バージョン 1703 以降の Windows Server 2016 および 2019 のコンピューターでサポートされます。
- ファイルのブロックを開始するには、まず [設定] で [ブロック] 機能または [許可 [**]** 機能を有効にする](advanced-features.md)必要があります。
- この機能は、疑わしいマルウェア (または悪意のある可能性のあるファイル) が Web からダウンロードされるのを防ぐために設計されています。 現在、.exe ファイルや _.dll_ ファイルを含むポータブル実行可能ファイル _(PE) ファイルがサポート_ されています。 対象範囲は時間の長い期間延長されます。

ネットワーク共有からローカル デバイスに大きなファイルをコピーする場合、特に VPN 接続を使用してパフォーマンスに影響を与える可能性があります。 

> [!IMPORTANT]
> - 許可またはブロックアクションの前にファイルの分類がデバイスのキャッシュに存在する場合は、ファイルに対して許可またはブロック関数を実行できません。 
> - 信頼できる署名付きファイルは、異なる方法で処理されます。 Defender for Endpoint は、悪意のあるファイルを処理するために最適化されています。 信頼できる署名付きファイルをブロックしようとすると、パフォーマンスに影響を与える場合があります。
> - 通常、ファイル ブロックは数分以内に適用されますが、30 分以上かかる場合があります。
> - ファイル インジケーター ポリシーが競合している場合は、より安全なポリシーの適用ポリシーが適用されます。 たとえば、両方のハッシュの種類が同じファイルを定義している場合、SHA-256 ファイル ハッシュ インジケーター ポリシーが MD5 ファイル ハッシュ インジケーター ポリシーよりも優先されます。

### <a name="create-an-indicator-for-files-from-the-settings-page"></a>設定ページからファイルのインジケーターを作成する

1. ナビゲーション ウィンドウで、[設定インジケーター]**を**  >  **選択します**。  

2. [ファイル ハッシュ **] タブを選択** します。

3. [インジケーター **の追加] を選択します**。

4. 次の詳細を指定します。
   - Indicator - エンティティの詳細を指定し、インジケーターの有効期限を定義します。
   - Action - 実行するアクションを指定し、説明を入力します。
   - Scope - コンピューター グループのスコープを定義します。

5. [概要] タブで詳細を確認し、[保存] を **クリックします**。

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a>ファイルの詳細ページからコンテキスト インジケーターを作成する
ファイルに対して応答アクションを実行 [する場合のオプションの 1](respond-file-alerts.md) つは、ファイルのインジケーターを追加することです。 

ファイルのインジケーター ハッシュを追加すると、組織内のコンピューターがファイルを実行しようとするたびに、アラートを発生してファイルをブロックできます。

インジケーターによって自動的にブロックされたファイルは、ファイルのアクション センターには表示されませんが、アラートはアラート キューに表示されます。


## <a name="related-topics"></a>関連項目
- [インジケーターの作成](manage-indicators.md)
- [IPs と URL/ドメインのインジケーターを作成する](indicator-ip-domain.md)
- [証明書に基づいてインジケーターを作成する](indicator-certificates.md)
- [インジケーターの管理](indicator-manage.md)
