<script>
  import FlipCard from "./components/FlipCard.svelte";
  import { Col, Container, Row } from "sveltestrap";
  import Fa from "svelte-fa/src/fa.svelte";
  import { faFlag, faPencilAlt, faCog, faInfo } from "@fortawesome/free-solid-svg-icons";
  import * as dataText from "./data/data.json";
  let textBundle = dataText.default
  console.log("textBundle",JSON.stringify(textBundle));
</script>

<svelte:head>
  <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css"
  />
</svelte:head>

<Container>
  <Row>
    {#each textBundle as sideCard}
      <Col>
        <FlipCard
          sideCardText={sideCard.sideCardText}
          backCardText={sideCard.backCardText}
          sideCardIcon={faFlag}
        />
      </Col>
    {/each}
  </Row>
</Container>
