---
title: クラウドのクラウド保護レベルを指定Microsoft Defender ウイルス対策
description: クラウド保護のレベルを設定して、Microsoft Defender ウイルス対策。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御、クラウド、攻撃性、保護レベル
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.date: 08/26/2021
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: deb4da81114e90d7bffbcc9642fef71c30a07f0d
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61165848"
---
# <a name="specify-the-cloud-protection-level"></a>クラウド保護レベルを指定する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender ウイルス対策

クラウド保護は、従来のセキュリティ インテリジェンスMicrosoft Defender ウイルス対策よりはるかに高速にエンドポイントに保護を提供するために、クラウド保護と共に機能します。 クラウド保護のレベルを構成するには、Microsoft エンドポイント マネージャー (推奨) またはグループ ポリシーを使用します。

> [!NOTE]
> [高 **]、[****高+]、** または [**ゼロ許容値**] を選択すると、一部の正当なファイルが検出される可能性があります。 その場合は、検出されたファイルのブロックを解除するか、検出されたファイルをポータルでMicrosoft 365 Defenderできます。

## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-protection"></a>クラウドMicrosoft エンドポイント マネージャーレベルを指定するには、次の情報を使用します。

1. 管理センター ( ) Microsoft エンドポイント マネージャーに移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、サインインします。

2. [エンドポイント **セキュリティウイルス** \> **対策] を選択します**。

3. ウイルス対策プロファイルを選択します。 (まだプロファイルを持っていない場合、または新しいプロファイルを作成する場合は、「デバイス制限設定を構成する」を参照[Microsoft Intune。](/intune/device-restrictions-configure)

4. [プロパティ **] を選択します**。 次に、[構成設定] **の横にある**[編集] を **選択します**。

5. [ **クラウド保護]** を展開し、[クラウド配信の保護レベル] ボックス **の一覧** で、次のいずれかを選択します。

    - **高**: 強力なレベルの検出を適用します。
    - **High plus**: High レベルを **使用し** 、追加の保護手段を適用します (クライアントのパフォーマンスに影響を与える可能性があります)。
    - **ゼロ許容値**: 不明なすべての実行可能ファイルをブロックします。

6. [ **確認] + [保存] の** 順に選択し、[保存] を **選択します**。

> [!TIP]
> いくつかのヘルプが必要ですか? 以下のリソースを参照してください。
>
> - [Endpoint Protection を構成する](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Intune でエンドポイント保護設定を追加する](/mem/intune/protect/endpoint-protection-configure)

## <a name="use-group-policy-to-specify-the-level-of-cloud-protection"></a>グループ ポリシーを使用してクラウド保護のレベルを指定する

1. グループ ポリシー管理マシンで、グループ ポリシー管理 [コンソールを開きます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。

3. グループ ポリシー **管理エディターで、[コンピューター** の構成 **] [管理** \> **用テンプレート] に移動します**。

4. MpEngine の [**コンポーネント] Windowsツリー** \> **Microsoft Defender ウイルス対策** \> **展開します**。

5. [クラウド保護レベルの **選択] 設定をダブルクリックし** 、[有効] に **設定します**。 保護のレベルを選択します。
    - **既定のブロック レベルは** 、正当なファイルを検出するリスクを高めることなく、強力な検出を提供します。
    - **中程度のブロック レベル** は、高信頼検出にのみ中程度を提供します
    - **高ブロック レベルでは** 、クライアントのパフォーマンスを最適化しながら強力なレベルの検出を適用します (ただし、誤検知の可能性も高くなる可能性があります)。
    - **高 + ブロック レベルは** 、追加の保護対策を適用します (クライアントのパフォーマンスに影響を与え、誤検知の可能性が高い可能性があります)。
    - **ゼロトレランス ブロック レベルは、** 不明なすべての実行可能ファイルをブロックします。

6. **[OK]** を選択します。

7. 更新されたグループ ポリシー オブジェクトを展開します。 「 [グループ ポリシー管理コンソール」を参照してください。](/windows/win32/srvnodes/group-policy)

> [!TIP]
> オンプレミスでグループ ポリシー オブジェクトを使用していますか? クラウドでの翻訳方法を確認します。 [[プレビュー] でグループ ポリシー分析を使用して、オンプレミスのグループ ポリシー Microsoft エンドポイント マネージャーを分析します](/mem/intune/configuration/group-policy-analytics)。 
  
## <a name="see-also"></a>関連項目

[クラウド保護を有効にする必要Microsoft Defender ウイルス対策](why-cloud-protection-should-be-on-mdav.md)
