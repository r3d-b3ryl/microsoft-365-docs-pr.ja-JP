---
title: Microsoft Defender for Endpoint とOffice 365 Microsoft Defender を使用する
f1.keywords:
- NOCSH
keywords: 統合, Microsoft Defender, Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Microsoft Defender for Office 365 Microsoft Defender for Endpoint を使用して、デバイスやメール コンテンツに対する脅威に関する詳細な情報を取得します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d54e4ec40c636b8b3ea319e79cbad5005850952
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029269"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint とOffice 365 Microsoft Defender を使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender for Office 365](defender-for-office-365.md)は[、Microsoft Defender for Endpoint で動作するように構成できます](/windows/security/threat-protection)。

Microsoft Defender for Office 365 Microsoft Defender for Endpoint と統合すると、セキュリティ運用チームがユーザーのデバイスが危険にさらされている場合に迅速に監視し、アクションを実行できます。 たとえば、統合が有効になると、セキュリティ運用チームは、検出された電子メール メッセージの影響を受ける可能性のあるデバイスと、Microsoft Defender for Endpoint のデバイスに対して生成された最近のアラートの数を確認できます。

次の図は、Microsoft Defender for **Endpoint** 統合を有効にした場合の [デバイス] タブの外観を示しています。

![Microsoft Defender for Endpoint が有効になっている場合は、通知を含むデバイスの一覧を表示できます。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

この例では、検出された電子メール メッセージの受信者が 4 つのデバイスを持ち、1 つはアラートを持っているのを確認できます。 デバイスのリンクをクリックすると、デバイスのページMicrosoft 365 Defender [(以前](../defender-endpoint/microsoft-defender-security-center.md)は Microsoft Defender セキュリティ センター) に表示されます。

> [!TIP]
> 新しいMicrosoft 365 Defenderポータルは、ユーザーを置き換Microsoft Defender セキュリティ センター。 「Microsoft [Defender for Endpoint in Microsoft 365 Defender」を参照してください](../defender/microsoft-365-security-center-mde.md)。

## <a name="requirements"></a>Requirements

- 組織には、Microsoft Defender for Office 365 (Office 365 E5) と Microsoft Defender for Endpoint が必要です。

- グローバル管理者か、セキュリティ管理者の役割 (セキュリティ管理者など) が管理者に割り当てられている必要Microsoft 365。 詳細については、「ポータルの[アクセス許可」をMicrosoft 365 Defenderしてください](permissions-microsoft-365-security-center.md)。

- エクスプローラー (またはリアルタイム検出) にアクセス [できる必要があります](threat-explorer.md)。

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Office 365エンドポイントと統合するには

Microsoft Defender for Endpoint Office 365 Microsoft Defender の統合は、Defender for Endpoint と Defender for Endpoint の両方Office 365。

1. グローバル管理者またはセキュリティ管理者として <https://security.microsoft.com/threatexplorer> 。

2. ナビゲーション ウィンドウで、[メール] を選択 **して&エクスプローラーを** \> **選択します**。

3. [エクスプローラー **] ページ** の画面の右上隅にある **[MDE** ファイル] をクリック設定。

4. 表示される **Microsoft Defender for Endpoint** 接続のフライアウトで、[エンドポイント用 Microsoft **Defender** Connect ] (トグルオン) をオンにし、[閉じる] アイコンをクリック ![ ](../../media/scc-toggle-on.png) ![ ](../../media/m365-cc-sc-close-icon.png) **します**。

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE 接続":::

5. ナビゲーション ウィンドウに戻り、[次へ]**を設定。** [エンドポイント]**設定[** エンドポイント]**を選択します。**

6. 開く **[エンドポイント] ページで** 、[高度な機能] **を選択します**。

7. [脅威インテリジェンス]**接続Office 365下に** スクロールし、オンにします ( ![ トグルオン ](../../media/scc-toggle-on.png) )。

   完了したら、[基本設定の保存] **をクリックします**。

## <a name="related-articles"></a>関連記事

[脅威の調査と対応機能 (Office 365](office-365-ti.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)

[Microsoft Defender for Endpoint](/windows/security/threat-protection)
