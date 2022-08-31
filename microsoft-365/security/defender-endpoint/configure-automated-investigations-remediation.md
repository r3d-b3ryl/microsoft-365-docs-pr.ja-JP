---
title: 自動調査と修復機能を構成する
description: Microsoft Defender for Endpointで自動調査と修復機能を設定します。
keywords: 構成、セットアップ、自動化、調査、検出、アラート、修復、応答
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 09d9860119a7c4aeb8949357b277fb395e09a9c2
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481902"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointで自動調査と修復機能を構成する

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Business](../defender-business/mdb-overview.md)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

組織が [Defender for Endpoint](/windows/security/threat-protection/) (または [Defender for Business](../defender-business/mdb-overview.md)) を使用している場合、 [自動調査と修復機能](/microsoft-365/security/defender-endpoint/automated-investigations) により、セキュリティ運用チームの時間と労力を節約できます。 [このブログ投稿](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)で説明したように、これらの機能は、セキュリティ アナリストが脅威を調査して修復するために実行する理想的な手順を模倣します。 [自動調査と修復の詳細については、こちらを参照してください](/microsoft-365/security/defender-endpoint/automated-investigations)。

自動調査と修復を構成するには:

1. [機能をオンにします](#turn-on-automated-investigation-and-remediation)。そして
2. [デバイス グループを設定します](#set-up-device-groups)。

## <a name="turn-on-automated-investigation-and-remediation"></a>自動調査と修復を有効にする

1. グローバル管理者またはセキュリティ管理者として、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、[ **設定]** を選択します。

3. **[エンドポイント]** を選択し、[**高度な機能**] を選択します。

4. **自動調査** と **アラートの自動解決の両方を** 有効にします。

## <a name="set-up-device-groups"></a>デバイス グループを設定する

> [!NOTE]
> この手順は、Defender for Business には適用されません。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) の **[設定]** ページの [**アクセス許可**] で、[**デバイス グループ**] を選択します。

2. [ **+ デバイス グループの追加]** を選択します。

3. 次のように、少なくとも 1 つのデバイス グループを作成します。

   - デバイス グループの名前と説明を指定します。
   - **[オートメーション] レベルの一覧** で、[**完全な脅威の修復**] などのレベルを自動的に選択します。 自動化レベルでは、修復アクションを自動的に実行するか、承認時にのみ実行するかを決定します。 詳細については、 [自動調査と修復の自動化レベルに](automation-levels.md)関するページを参照してください。
   - [ **メンバー]** セクションで、1 つ以上の条件を使用してデバイスを識別して含めます。
   - [ **ユーザー アクセス** ] タブで、作成するデバイス グループにアクセスする必要がある [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) グループを選択します。

4. デバイス グループの設定が完了したら、[ **完了] を** 選択します。

## <a name="next-steps"></a>次の手順

- [アクション センターにアクセスして、保留中の修復アクションと完了した修復アクションを表示する](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [保留中のアクションを確認して承認する](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Endpoint での誤検出/検出漏れに対処する](defender-endpoint-false-positives-negatives.md)
