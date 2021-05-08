---
title: Microsoft Defender ウイルス対策のクラウド配信の保護レベルを指定する
description: Microsoft Defender ウイルス対策のクラウド配信保護のレベルを設定します。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御、クラウド、攻撃性、保護レベル
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f441b1bd444cd70fb5b00dfcb5ebcddadf62b220
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274906"
---
# <a name="specify-the-cloud-delivered-protection-level"></a>クラウドによる保護レベルを指定する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus が提供するクラウド配信保護のレベルは、Microsoft Endpoint Manager (推奨) またはグループ ポリシーを使用して指定できます。

> [!TIP]
> クラウド保護は、単にクラウドに保存されているファイルの保護ではありません。 Microsoft Defender Antivirus クラウド サービスは、ネットワークとデバイス (エンドポイントとも呼ばれる) に更新された保護を提供するためのメカニズムです。 Microsoft Defender Antivirus によるクラウド保護では、分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。 Microsoft Intune と Microsoft エンドポイント マネージャーは、Microsoft エンドポイント マネージャー [の一部です](/mem/endpoint-manager-overview)。 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a>Microsoft Endpoint Manager を使用してクラウド配信保護のレベルを指定する

1. Microsoft Endpoint Manager 管理センター ( ) に移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、サインインします。

2. [エンドポイント **セキュリティウイルス**  >  **対策] を選択します**。

3. ウイルス対策プロファイルを選択します。 (まだプロファイルを持っていない場合、または新しいプロファイルを作成する場合は、「デバイス制限設定を Microsoft Intune で構成する」 [を参照してください](/intune/device-restrictions-configure)。

4. [プロパティ **] を選択します**。 次に、[構成設定] **の横にある**[編集] を **選択します**。

5. [ **クラウド保護]** を展開し、[クラウド配信の保護レベル] ボックス **の一覧** で、次のいずれかを選択します。

    1. **高**: 強力なレベルの検出を適用します。
    2. **High plus**: High level **を使用し** 、追加の保護手段を適用します (クライアントのパフォーマンスに影響を与える可能性があります)。
    3. **ゼロ許容値**: 不明なすべての実行可能ファイルをブロックします。

6. [ **確認] + [保存] の** 順に選択し、[保存] を **選択します**。 

> [!TIP]
> いくつかのヘルプが必要ですか? 以下のリソースを参照してください。
> - [エンドポイント保護の構成](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Intune でエンドポイント保護設定を追加する](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a>グループ ポリシーを使用してクラウド配信保護のレベルを指定する

1.  グループ ポリシー管理マシンで、グループ ポリシー管理 [コンソールを開きます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **クリックします**。

3.  グループ ポリシー **管理エディターで、[コンピューター** の構成 **] [管理**  >  **用テンプレート] に移動します**。

4.  ツリーを **Windows コンポーネント Microsoft** Defender ウイルス対策  >    >  **MpEngine に展開します**。

5.  [クラウド保護レベルの **選択] 設定をダブルクリックし** 、[有効] に **設定します**。 保護のレベルを選択します。
    - **既定のブロック レベルは** 、正当なファイルを検出するリスクを高めることなく、強力な検出を提供します。
    - **中程度のブロック レベル** は、高信頼検出にのみ中程度を提供します
    - **高ブロック レベルでは** 、クライアントのパフォーマンスを最適化しながら強力なレベルの検出を適用します (ただし、誤検知の可能性も高くなる可能性があります)。
    - **高 + ブロック レベルは** 、追加の保護対策を適用します (クライアントのパフォーマンスに影響を与え、誤検知の可能性を高める可能性があります)。
    - **ゼロトレランス ブロック レベルは、** 不明なすべての実行可能ファイルをブロックします。
    
    > [!WARNING]
    > このスイッチを High またはHigh **+** に設定すると、一部の正当なファイルが検出される可能性があります (ただし、その検出のブロックを解除または争うオプションがあります)。

6. [**OK**] をクリックします。

7. 更新されたグループ ポリシー オブジェクトを展開します。 「 [グループ ポリシー管理コンソール」を参照してください。](/windows/win32/srvnodes/group-policy)

> [!TIP]
> オンプレミスでグループ ポリシー オブジェクトを使用していますか? クラウドでの翻訳方法を確認します。 Microsoft Endpoint Manager - Preview でグループ ポリシー分析を使用して、[オンプレミスのグループ ポリシー オブジェクトを分析します](/mem/intune/configuration/group-policy-analytics)。 
  
## <a name="related-articles"></a>関連記事

- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
- [クラウドによる保護を有効にする](enable-cloud-protection-microsoft-defender-antivirus.md)
- [マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)