---
title: Microsoft Defender for Endpoint とOffice 365 Microsoft Defender を使用する
f1.keywords:
- NOCSH
keywords: 統合, Microsoft Defender, Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
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
ms.openlocfilehash: 3f1d92d2433267b89398c7f7f582a8d1ee8cdba5
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878606"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint とOffice 365 Microsoft Defender を使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender for Office 365](defender-for-office-365.md)は[、Microsoft Defender for Endpoint で動作するように構成できます](/windows/security/threat-protection)。

Microsoft Defender for Office 365 Microsoft Defender for Endpoint と統合すると、セキュリティ運用チームがユーザーのデバイスが危険にさらされている場合に迅速に監視し、アクションを実行できます。 たとえば、統合が有効になると、セキュリティ運用チームは、検出された電子メール メッセージの影響を受ける可能性のあるデバイスと、Microsoft Defender for Endpoint のデバイスに対して生成された最近のアラートの数を確認できます。

次の図は、Microsoft Defender for **Endpoint** 統合を有効にした場合の [デバイス] タブの外観を示しています。

![Microsoft Defender for Endpoint が有効になっている場合は、通知を含むデバイスの一覧を表示できます。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

この例では、検出された電子メール メッセージの受信者が 4 つのデバイスを持ち、1 つはアラートを持っているのを確認できます。 デバイスのリンクをクリックすると、デバイスのページが [Microsoft Defender セキュリティ センター ( ) で開きます <https://securitycenter.windows.com> 。

> [!TIP]
> **[詳しくは、Microsoft Defender セキュリティ センター](/windows/security/threat-protection/microsoft-defender-atp/use)** (Microsoft Defender for Endpoint ポータルとも呼ばれます)をご覧ください。

## <a name="requirements"></a>要件

- 組織には、Microsoft Defender for Office 365 (Office 365 E5) と Microsoft Defender for Endpoint が必要です。

- グローバル管理者またはセキュリティ管理者の役割 (セキュリティ管理者など) がセキュリティ コンプライアンス センターに割り当てられている& [必要があります](https://protection.office.com)。 (「 [セキュリティ コンプライアンス センターのアクセス許可&」を参照してください](permissions-in-the-security-and-compliance-center.md))

- セキュリティ コンプライアンス センターとセキュリティ コンプライアンス センターの[エクスプローラー (](threat-explorer.md)またはリアルタイム検出) の両方にアクセス&必要Microsoft Defender セキュリティ センター。

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Office 365エンドポイントと統合するには

Microsoft Defender for Office 365 Microsoft Defender for Endpoint との統合は、セキュリティ コンプライアンス センターとセキュリティ コンプライアンス センターの両方&使用してMicrosoft Defender セキュリティ センター。

1. グローバル管理者またはセキュリティ管理者として、アクセスして <https://protection.office.com> サインインします。 (これにより、コンプライアンス センター Office 365セキュリティ &にアクセスします。

2. ナビゲーション ウィンドウで、[脅威管理エクスプローラー] **を** \> **選択します**。

   ![[脅威の管理] メニューの [エクスプローラー]](../../media/ThreatMgmt-Explorer-nav.png)

3. 画面の右上隅で、[Defender **for Endpoint 設定 (MDE 設定) を選択します**。

4. [Microsoft Defender for Endpoint 接続] ダイアログ ボックスで、[エンドポイント用 Microsoft Defender Connect **を有効にします**。

   ![エンドポイント接続用 Microsoft Defender](../../media/Explorer-WDATPConnection-dialog.png)

5. [ ] ( ) のMicrosoft Defender セキュリティ センター移動 <https://securitycenter.windows.com> します。

6. ナビゲーション バーで、[次へ]**を設定。** 次に、[全般] **で 、[** 高度な機能 **] を選択します**。

7. [脅威インテリジェンス]**接続Office 365下にスクロールし**、接続をオンにしてください。

   ![Office 365インテリジェンス接続](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>関連資料

[脅威の調査と対応機能 (Office 365](office-365-ti.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)

[Microsoft Defender for Endpoint](/windows/security/threat-protection)
