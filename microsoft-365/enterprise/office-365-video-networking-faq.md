---
title: Office 365ビデオ ネットワークに関するよく寄せられる質問
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/14/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 2bed67a1-4052-49ff-a4ce-b7e6530eb98e
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: 帯域幅の計画、暗号化、サービスによるコンテンツ配信ネットワーク (CDN) の活用方法に関する最も&質問に対する回答を見つける。
ms.openlocfilehash: 8bc0a69ff744967d24aa7d21ed6daee1a839f159
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921572"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Office 365ビデオ ネットワークに関するよく寄せられる質問

ビデオ Office 365ストリーミング サービスを使用すると、組織内でのビデオの保存とストリーミングが簡単になります。 ビデオに関する多[くのOffice 365があります](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)。このネットワークに関する FAQ は、帯域幅の計画、暗号化、およびサービスがコンテンツ配信ネットワーク[](content-delivery-networks.md) (CDN) を活用する方法に関する最も一般的な質問に答える目的で設計されています。
  
ビデオがアップロードまたは再生された場合に何が起こるかについて十分に理解していない場合は、このビデオを一緒に見てみましょう。Office 365 ビデオにアップロードするとビデオ[ファイルに何が](https://www.youtube.com/watch?v=HXSZ0jYBKlM)起こるか。
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>ビデオ帯域幅の要件Office 365は何ですか?

サポートされている多数[のビデオ形式は](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817)、ユーザーにアップロードOffice 365。 その後、各ビデオ ファイルは、再生用にいくつかの異なるビデオ品質を持つ標準形式にエンコードされます。 Office 365ビデオでは、アダプティブ ビットレート ストリーミングを使用して、利用可能なネットワーク帯域幅とビデオ プレーヤーのサイズに基づいて最適なビデオ再生品質を選択します。 これを行うには、プレイヤーは最初に最も低い再生品質を要求します。 その後、サービスはビデオ プレーヤーに 2 秒間のビデオ セグメントの送信を開始します。 プレイヤーは、各セグメントの配信速度に基づいて、より高い再生品質または低い再生品質を要求できます。
  
アダプティブ ビットレート ストリーミングは、ビデオが中断やバッファー処理の最小量で再生されている間、バックグラウンドでこのすべての処理を行います。 ビデオ再生中に、ビデオ プレーヤーは、ビューアーが手動で自動再生品質を上書きして、特定のビデオ再生品質を選択できます。
  
ビデオ再生の各品質のネットワーク要件の概要を示す簡単な表を次に示します。 ビデオの再生に必要な 1 人あたりの最小帯域幅は 802Kbps です。
  
| 再生品質 | ネットワーク速度 |
|:-----|:-----|
|288p  <br/> |802Kbps  <br/> |
|360p  <br/> |1.2 Mbps  <br/> |
|576p  <br/> |2.5 Mbps  <br/> |
|720p  <br/> |3.8 Mbps  <br/> |

([トップに戻る](office-365-video-networking-faq.md))
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>コンテンツ配信ネットワーク (CDN) はビデオの再生にどう役立ちますか?

同じ地理的な場所内の同じ組織の複数のユーザーが同じビデオをストリーミングしている場合、CDN は、これらのビデオのコピーをその地理的地域に近い場所に保存します。 ビデオを保存するか、最も近い場所にキャッシュすると、各ユーザーは、遠く離れた場所ではなく、最も近い場所からビデオをストリーミングします。 Office 365ビデオでは、Azure Media Servicesを使用して、Azure CDN にキャッシュされるコンテンツと、その期間を管理します。 Azure Media Services任意の場所をAzure CDN、数日間[](/azure/cdn/cdn-pop-locations)ビデオ フラグメントとマニフェストをキャッシュできます。 組織内のユーザーがキャッシュされたビデオを引き続き視聴する場合、キャッシュに残されます。 数日間ビデオにアクセスするユーザーがいない場合、ビデオは最終的にキャッシュから削除されます。 次回、誰かがビデオを視聴しようとすると、最も近い場所に再びCDNされます。
  
コンテンツが近くの CDN でキャッシュされている間にビデオを視聴しようとするすべてのユーザーは、ビデオが近く、ほとんどの場合ホップが少なく、離れて行くメリットがあります。 これにより、ビデオの再生速度が向上します。ただし、ビデオを再生するネットワーク要件は変更されません。
  
> [!NOTE]
> 容量制限に達した場合など、3 日前にビデオが削除される場合があります。
  
([トップに戻る](office-365-video-networking-faq.md))
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>高速再生のためにビデオをローカルにキャッシュできますか?

はい。 Office 365、ローカル CDN またはキャッシュ プロキシを使用して、ビデオや他の Office 365 コンテンツをローカル ネットワークに持ち込み、アクセスを高速化できます。 ネットワークにローカル キャッシュ ソリューションを実装するにはいくつかの方法があります。最も一般的な方法は、コンテンツをローカルにキャッシュするプロキシ ソリューションを使用する方法です。 プロキシまたはプライベート CDN がビデオ フラグメントとマニフェストをキャッシュすると、プロキシまたはプライベート CDN を経由するファイルに対する今後の要求はローカル キャッシュから引き出され、インターネットの場所から引き出されません。 このようなソリューションの計画中に、ネットワーク帯域幅、容量、ビデオ再生の同時実行を検討します。
  
([トップに戻る](office-365-video-networking-faq.md))
  
## <a name="how-videos-are-encrypted-and-secured"></a>ビデオの暗号化とセキュリティ保護の方法

Office 365ビデオでは、データを安全かつプライベートに保つ必要がある点が分かっています。 [Microsoft Trust Center では](https://products.office.com/business/office-365-trust-center-welcome) 、コンテンツのプライバシーとセキュリティに対する取り組みについて説明します。 ビデオの再生では、優れたエクスペリエンスを実現するには速度が重要です。ただし、速度と引き換えにセキュリティやプライバシーは侵害しません。 速度、セキュリティ、プライバシーに対応する方法を次に示します。
  
組織内のユーザーが新しいビデオをアップロードすると、そのビデオはトランスコードされ、AES-128 暗号化で暗号化され、Azure Media Services に保存されます。 つまり、ビデオは転送中と保存時の両方で暗号化されます。
  
組織内のユーザーが新しいビデオを視聴しようとすると、次の手順に従います。
  
1. ビデオSharePointアクセス許可を持っている場合は、オンラインで確認します。

2. SharePointオンラインでは、ファイルのアクセス許可を使用して、ユーザーがビデオを視聴できるかどうかを判断します。

3. 許可されている場合、SharePointオンラインは Azure からトークンを取得してビデオ プレーヤーに渡します。

4. その後、ビデオ プレーヤーはトークンを使用して Azure から復号化キーを要求します。

5. 復号化キーを手にして、ビデオ プレーヤーはビデオをストリーミングできます。

![O365 ビデオ再生](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
([トップに戻る](office-365-video-networking-faq.md))
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>ビデオを再生する場合のOffice 365ですか?

Office 365ビデオでサポートされるオペレーティング システムと Web ブラウザーは、システム要件にSharePointオンライン要件Office 365[同じです](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45)。 どのオペレーティング システムと Web ブラウザーの構成に応じて、ビデオ プレーヤーの特定のニーズが決定されます。 ビデオ再生の要件の [詳細については、次の情報を参照してください](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)。
  
([トップに戻る](office-365-video-networking-faq.md))
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>ビデオを動作Office 365できない場合は、どこから始める必要がありますか?

ビデオへの接続Office 365トラブルシューティングには、ネットワーク、ISP、およびデバイスの構成のトラブルシューティングがOffice 365。 最初に開始する場所は、サービス正常性ダッシュボードです。 これにより、ビデオに問題Office 365問題が発生している可能性が示されます。 すべてが見栄えの良い場合は、役立つ追加のリソースを次に示します。
  
- ビデオに必要なネットワーク エンドポイントに接続[Office 365します](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)。

- ネットワークのトラブルシューティング ガイドを使用して[、ネットワークOffice 365を確認します](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)。

- 低速の[ネットワークでネットワークを使用するためのベスト Office 365を参照してください](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)。

- [ビデオ構成に関するOffice 365を確認します](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)。

([トップに戻る](office-365-video-networking-faq.md))
  
## <a name="office-365-video-resources"></a>Office 365ビデオ リソース

ビデオの展開と使用を正常に行うのに役立つその他のOffice 365示します。
  
[ビデオ構成に関するOffice 365検索](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[Office 365 ビデオを利用する](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[ビデオでチャネルを作成およびOffice 365する](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[Office 365 ビデオ ポータルを管理する](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[ビデオで動作するビデオ形式Office 365ビデオ](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
([トップに戻る](office-365-video-networking-faq.md))
  
ここに戻る場合は、次の短いリンクをご利用ください: [https://aka.ms/video365networkfaq]()