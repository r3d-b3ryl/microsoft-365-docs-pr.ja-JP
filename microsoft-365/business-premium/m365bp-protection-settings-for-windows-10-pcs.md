---
title: Windows 10 PC のデバイス保護設定を編集または作成する
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
- adminvideo
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Windows 10 デバイスをセキュリティで保護するために、ビジネス向けのMicrosoft 365で使用できる設定について説明します。
ms.openlocfilehash: ef4df7b308c52275db8d43c1c0619a64594ed690
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096244"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a>Windows 10 PC のデバイス保護設定を編集または作成する

この記事は Microsoft 365 Business Premium に適用されます。

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日以降、Microsoft 365 Business Premium のお客様に展開されます。 このオファリングでは、デバイスに追加のセキュリティ機能が提供されます。 [Defender for Business の詳細については、こちらをご覧ください](../security/defender-business/mdb-overview.md)。

[セットアップ] ページで既定の Windows 保護設定を設定したら、すべてのユーザーまたは一連のユーザーに適用される新しい保護設定を追加できます。 作成した任意のファイルを編集することもできます。

## <a name="watch-create-protection-settings-for-windows-10-devices"></a>Windows 10 デバイスのアプリケーション保護設定を設定する

Microsoft 365 Business で Windows 10 デバイスをセキュリティで保護する方法のビデオを表示します。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。 

2. 左側のナビゲーションで、**[デバイス]** \> **[ポリシー]**\>**[追加]** を選択します。

3. [ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。 

4. [ **ポリシーの種類**] で、[ **Windows 10 デバイスの構成**] を選びます。

5. **[Windows 10 デバイスをセキュリティで保護する]** \>を展開し、好みの設定を構成します。詳細については、「[利用可能な設定](#available-settings)」をご覧ください。 
    
    [ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。 
    
    ![Windows 10 デバイスの構成が選択された [ポリシーの追加] ウィンドウ。](./../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.

7. 最後に、[ **完了**] を選択してポリシーを保存し、それをデバイスに割り当てます。 

## <a name="edit-windows-10-protection-settings"></a>Windows 10 保護設定を編集する
 
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。     

2. 左側のナビゲーションで、**[デバイス]** \> **[ポリシー]** を選択します。

3. 既存の Windows デバイス ポリシーを選択してから、**[編集]** を選択します。

4. 変更する設定の横にある **[編集]** を選択してから、**[保存]** を選択します。

## <a name="available-settings"></a>利用可能な設定

既定では、すべての設定が **オン** になっています。次の設定を使用できます。
  
詳細については、「[Microsoft 365 Premium の保護機能を Intune の設定に対応付ける方法](m365bp-map-protection-features-to-intune-settings.md)」をご覧ください。 


|Setting  |説明  |
|:-----|:-----|
|Windows Defender ウイルス対策を使用して PC をウイルスとその他の脅威から保護する  |インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。  |
|Microsoft Edge で PC を Web ベースの脅威から保護する  |ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。  |
|デバイスに対する攻撃を回避するルールを使用する  |オンにすると、攻撃の回避により、デバイス感染のためにマルウェアが通常使用するアクションやアプリをブロックすることができます。Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。詳細については、「[攻撃の回避](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)」を参照してください。    |
|ランサムウェアなどの脅威からフォルダーを保護する  |この設定は、フォルダーへのアクセスを制御することによって、ランサムウェアなどの不審なまたは悪意のあるアプリケーションによる書き換えから会社のデータを保護します。こうした種類のアプリケーションは、保護されているフォルダーで変更を行うことができないようにブロックされます。Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。詳細については、「[フォルダーへのアクセス制御でフォルダーを保護する](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA)」を参照してください。    |
|インターネット上の悪意がある可能性のあるコンテンツに対するネットワーク アクセスを防止する  |この設定を使用すると、フィッシング詐欺、攻撃、またはその他の悪意のあるコンテンツをホストしている可能性がある低評価のインターネット上の場所へのユーザーの外部接続をブロックします。Windows Defender ウイルス対策が **[オン]** に設定されている場合にのみこの設定を利用できます。詳細については、「[ネットワークを保護する](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)」を参照してください。    |
|不正なアクセスから PC のファイルとフォルダーを保護するために BitLocker を使用する  |BitLocker は、コンピューターのハード ドライブを暗号化することによってデータを保護し、コンピューターの紛失や盗難時にデータの漏えいを防ぎます。詳細については、「[Bitlocker についてよく寄せられる質問](/windows/security/information-protection/BitLocker/BitLocker-frequently-asked-questions)」を参照してください。    |
|ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する  |ユーザーが Microsoft Storeからアプリをダウンロードしてインストールできるようにします。アプリにはゲームから生産性向上ツールまであらゆるものが含まれるため、この設定を **オン** のままにしていますが、セキュリティを強化するためにオフにすることもできます。    |
|ユーザーが Cortana にアクセスすることを許可する  |Cortana は非常に役に立つ場合があります。Cortana によって設定をオンまたはオフにしたり、手順を示したり、ユーザーが予定に間に合うようにしたりすることができるため、既定では、Microsoft はこの設定を **[オン]** にしています。    |
|ユーザーが Microsoft から Windows のヒントと広告を受け取ることを許可する  |Windows のヒントは役に立つ場合があり、新機能がリリースされたときにユーザーが適応するのに役立ちます。  |
|Windows 10 デバイスを自動的に最新の状態に維持する  |Windows 10 デバイスが、最新の更新プログラムを自動的に受け取るようにします。  |
|この時間アイドル状態になったときにデバイスの画面をオフにする  |ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーは、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりして、デバイスが無作為な視線に対して無防備な状態になってしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。  |

## <a name="see-also"></a>関連項目

[ビジネス プラン用に Microsoft 365 をセキュリティで保護する上位 10 の方法](../admin/security-and-compliance/secure-your-business-data.md) 