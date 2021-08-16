---
title: クラウド配信の保護レベルを指定Microsoft Defender ウイルス対策
description: クラウドによる保護のレベルを設定して、Microsoft Defender ウイルス対策。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御、クラウド、攻撃性、保護レベル
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 6b7ef857e09e01a1a9ba550dc679708c88dfce1751cd2644156ce38d1b8f42c6
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53863489"
---
# <a name="specify-the-cloud-delivered-protection-level"></a>クラウドによる保護レベルを指定する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

グループ ポリシー (推奨) またはグループ ポリシーを使用して、Microsoft Defender ウイルス対策によって提供されるMicrosoft エンドポイント マネージャーのレベルを指定できます。

> [!TIP]
> クラウド保護は、単にクラウドに保存されているファイルの保護ではありません。 クラウド Microsoft Defender ウイルス対策は、ネットワークとデバイス (エンドポイントとも呼ばれる) に更新された保護を提供するメカニズムです。 クラウド保護はMicrosoft Defender ウイルス対策分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。 Microsoft IntuneとMicrosoft エンドポイント マネージャーは、現在、Microsoft エンドポイント マネージャー に[含Microsoft エンドポイント マネージャー。](/mem/endpoint-manager-overview) 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a>クラウドMicrosoft エンドポイント マネージャー保護のレベルを指定するには、次の情報を使用します。

1. 管理センター ( ) Microsoft エンドポイント マネージャーに移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、サインインします。

2. [エンドポイント **セキュリティウイルス**  >  **対策] を選択します**。

3. ウイルス対策プロファイルを選択します。 (まだプロファイルを持っていない場合、または新しいプロファイルを作成する場合は、「デバイス制限設定を構成する」を参照[Microsoft Intune。](/intune/device-restrictions-configure)

4. [プロパティ **] を選択します**。 次に、[構成設定] **の横にある**[編集] を **選択します**。

5. [ **クラウド保護]** を展開し、[クラウド配信の保護レベル] ボックス **の一覧** で、次のいずれかを選択します。

    1. **高**: 強力なレベルの検出を適用します。
    2. **High plus**: High level **を使用し** 、追加の保護手段を適用します (クライアントのパフォーマンスに影響を与える可能性があります)。
    3. **ゼロ許容値**: 不明なすべての実行可能ファイルをブロックします。

6. [ **確認] + [保存] の** 順に選択し、[保存] を **選択します**。 

> [!TIP]
> いくつかのヘルプが必要ですか? 以下のリソースを参照してください。
> - [Endpoint Protection を構成する](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Intune でエンドポイント保護設定を追加する](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a>グループ ポリシーを使用してクラウド配信保護のレベルを指定する

1.  グループ ポリシー管理マシンで、グループ ポリシー管理 [コンソールを開きます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **クリックします**。

3.  グループ ポリシー **管理エディターで、[コンピューター** の構成 **] [管理**  >  **用テンプレート] に移動します**。

4.  MpEngine の [**コンポーネント] Windowsツリー**  >  **Microsoft Defender ウイルス対策**  >  **展開します**。

5.  [クラウド保護レベルの **選択] 設定をダブルクリックし** 、[有効] に **設定します**。 保護のレベルを選択します。
    - **既定のブロック レベルは** 、正当なファイルを検出するリスクを高めることなく、強力な検出を提供します。
    - **中程度のブロック レベル** は、高信頼検出にのみ中程度を提供します
    - **高ブロック レベルでは** 、クライアントのパフォーマンスを最適化しながら強力なレベルの検出を適用します (ただし、誤検知の可能性も高くなる可能性があります)。
    - **高 + ブロック レベルは** 、追加の保護対策を適用します (クライアントのパフォーマンスに影響を与え、誤検知の可能性を高める可能性があります)。
    - **ゼロトレランス ブロック レベルは、** 不明なすべての実行可能ファイルをブロックします。
    
    > [!WARNING]
    > このスイッチを High またはHigh **+** に設定すると、一部の正当なファイルが検出される可能性があります (ただし、その検出のブロックを解除または争うオプションがあります)。

6. **[OK]** をクリックします。

7. 更新されたグループ ポリシー オブジェクトを展開します。 「 [グループ ポリシー管理コンソール」を参照してください。](/windows/win32/srvnodes/group-policy)

> [!TIP]
> オンプレミスでグループ ポリシー オブジェクトを使用していますか? クラウドでの翻訳方法を確認します。 [[プレビュー] でグループ ポリシー分析を使用して、オンプレミスのグループ ポリシー Microsoft エンドポイント マネージャーを分析します](/mem/intune/configuration/group-policy-analytics)。 
  
## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)
- [マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)