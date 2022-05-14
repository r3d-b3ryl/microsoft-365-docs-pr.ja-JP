---
title: Microsoft Defender ウイルス対策のクラウド保護レベルを指定する
description: Microsoft Defender ウイルス対策に対するクラウド保護のレベルを設定します。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、Defender、クラウド、攻撃性、保護レベル
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
ms.openlocfilehash: 1f71e5cc2a944ce409a19b6493bda1b40747a066
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65417482"
---
# <a name="specify-the-cloud-protection-level"></a>クラウド保護レベルを指定する

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

クラウド保護は、Microsoft Defender ウイルス対策と連携して、従来のセキュリティ インテリジェンス更新を通じてより速くエンドポイントに保護を提供します。 Microsoft エンドポイント マネージャー (推奨) またはグループ ポリシーを使用して、クラウド保護のレベルを構成できます。

> [!NOTE]
> **[高]**、[**高 +**]、または **[ゼロ] の許容範囲** を選択すると、一部の正当なファイルが検出される可能性があります。 その場合は、検出されたファイルのブロックを解除するか、Microsoft 365 Defender ポータルでその検出に関する問題を解決できます。

## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-protection"></a>Microsoft エンドポイント マネージャーを使用してクラウド保護のレベルを指定する

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、サインインします。

2. **[エンドポイント セキュリティ** \> **ウイルス対策**] を選択します。

3. ウイルス対策プロファイルを選択します。 (まだお持ちでない場合、または新しいプロファイルを作成する場合は、「[Microsoft Intuneでデバイス制限設定を構成する](/intune/device-restrictions-configure)」を参照してください。

4. [**プロパティ**] をクリックします。 **[構成設定]** の横にある **[編集]** を選択します。

5. **[クラウド保護**] を展開し、[**クラウド配信の保護レベル**] ボックスの一覧で、次のいずれかを選択します。

    - **未構成**: 既定の状態。
    - **高**: 強力なレベルの検出を適用します。
    - **高いプラス**: **高** レベルを使用し、追加の保護手段を適用します (クライアントのパフォーマンスに影響を与える可能性があります)。
    - **ゼロ トレランス**: 不明な実行可能ファイルをすべてブロックします。

6. **[確認と保存]** を選択し、**[保存]** を選択します。

> [!TIP]
> ヘルプが必要ですか? 以下のリソースを参照してください。
>
> - [Endpoint Protection を構成する](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Intuneにエンドポイント保護設定を追加する](/mem/intune/protect/endpoint-protection-configure)

## <a name="use-group-policy-to-specify-the-level-of-cloud-protection"></a>グループ ポリシーを使用してクラウド保護のレベルを指定する

1. グループ ポリシー管理マシンで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

3. **グループ ポリシー管理エディター** で、**コンピューター構成** \> **管理テンプレート** に移動します。

4. ツリーを展開して、**MpEngine** **Microsoft Defender ウイルス対策コンポーネント** \> **をWindows**\>します。

5. **[クラウド保護レベルの選択]** 設定をダブルクリックし、[**有効]** に設定します。 保護レベルを選択します。

    - **未構成**: 既定の状態。
    - **既定のブロック レベル** では、正当なファイルを検出するリスクを高めることなく、強力な検出が提供されます。
    - **中程度のブロック レベル** は、信頼度の高い検出に対してのみ中等度を提供します
    - **高いブロック レベル** では、クライアントのパフォーマンスを最適化しながら強力なレベルの検出が適用されます (ただし、誤検知の可能性が高くなる可能性もあります)。
    - **高 + ブロック レベル** では、追加の保護手段が適用されます (クライアントのパフォーマンスに影響を与え、誤検知の可能性が高くなる可能性があります)。
    - **ゼロ トレランス ブロック レベル** では、すべての不明な実行可能ファイルがブロックされます。

6. **[OK]** を選択します。

7. 更新した グループ ポリシー オブジェクトをデプロイします。 [グループ ポリシー管理コンソールを](/windows/win32/srvnodes/group-policy)参照してください

> [!TIP]
> グループ ポリシー オブジェクトをオンプレミスで使用していますか? クラウドで翻訳する方法を確認します。 [Microsoft エンドポイント マネージャー - プレビューのグループ ポリシー分析を使用して、オンプレミス のグループ ポリシー オブジェクトを分析](/mem/intune/configuration/group-policy-analytics)します。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
  
## <a name="see-also"></a>関連項目

[Microsoft Defender ウイルス対策に対してクラウド保護を有効にする必要がある理由](why-cloud-protection-should-be-on-mdav.md)
