<template>
  <div class="content">
    <base-block rounded content-full>
      <b-form>
        <h2>Stammdaten</h2>
        <b-row class="push">
          <b-col lg="6">
            <h4>Kontakatinformationen</h4>
            <b-form-group label="Kunde" label-for="Kunde">
              <b-form-input id="Kunde" placeholder="Kunde"></b-form-input>
            </b-form-group>
            <b-form-group label="Lieferadresse" label-for="Lieferadresse">
              <b-form-select id="Lieferadresse" v-model="selected" :options="options" plain></b-form-select>
            </b-form-group>
            <b-form-group label="Postadresse" label-for="Postadresse">
              <b-form-select id="Postadresse" v-model="selected" :options="options" plain></b-form-select>
            </b-form-group>
            <b-form-group label="Rechnungsadresse" label-for="Rechnungsadresse">
              <b-form-select id="Rechnungsadresse" v-model="selected" :options="options" plain></b-form-select>
            </b-form-group>
          </b-col>
          <b-col lg="6">
            <h4>info</h4>
            <b-form-group label="Titel" label-for="Titel">
              <b-form-input id="Titel" placeholder="Titel"></b-form-input>
            </b-form-group>
            <b-form-group label="Angebotsnummer" label-for="Angebotsnummer">
              <b-form-input id="Angebotsnummer" placeholder="Angebotsnummer"></b-form-input>
            </b-form-group>
            <b-form-group label="Datum" label-for="Datum">
              <b-form-input id="Datum" placeholder="Datum" disabled></b-form-input>
            </b-form-group>
            <b-form-group label="Mitarbeiter" label-for="Mitarbeiter">
              <b-form-select id="Mitarbeiter" v-model="selected" :options="options" plain></b-form-select>
            </b-form-group>
            <b-form-group label="Status" label-for="Status">
              <b-form-select id="Status" v-model="selected" :options="options" plain></b-form-select>
            </b-form-group>
          </b-col>
        </b-row>
        <h2>Kopfzeile</h2>
        <b-row class="push">
          <b-col>
            <b-form-textarea id="example-textarea-input" rows="4" placeholder="Textarea content.."></b-form-textarea>
          </b-col>
        </b-row>
        <h2>Angebotspositionen</h2>
        <b-row class="push">
          <b-col>
            <base-block rounded>
              <b-table-simple responsive hover table-class="table-vcenter">
                <b-thead>
                  <b-tr>
                    <b-th>POSITION</b-th>
                    <b-th>#</b-th>
                    <b-th style="width: 7%;">Name</b-th>
                    <b-th>MENGE</b-th>
                    <b-th>EINZELPREIS</b-th>
                    <b-th>RABATT</b-th>
                    <b-th>EUR</b-th>
                    <b-th>GESAMTPREIS</b-th>
                    <b-th class="text-center" style="width: 100px;">Actions</b-th>
                  </b-tr>
                </b-thead>
                <b-tbody>
                  <b-tr>
                    <b-td colspan="9">
                      <b-col sm="6" xl="4">
                        <b-dropdown id="dropdown-default-success" variant="success" text="Elemente+">
                          <b-dropdown-item class="font-size-sm">Action</b-dropdown-item>
                          <b-dropdown-item class="font-size-sm">Another action</b-dropdown-item>
                          <b-dropdown-divider></b-dropdown-divider>
                          <b-dropdown-item class="font-size-sm">Something else here</b-dropdown-item>
                        </b-dropdown>
                      </b-col>
                    </b-td>
                  </b-tr>
                  <b-tr v-for="user in users.slice(0, 6)" :key="user.id">
                    <b-td>
                    </b-td>
                    <b-td>
                      {{ user.id }}
                    </b-td>
                    <b-td class="font-w600 font-size-sm">
                      {{ user.name }}
                    </b-td>
                    <b-td>
                      <b-input-group append="lfm">
                        <b-form-input type="text" value="s"></b-form-input>
                      </b-input-group>
                    </b-td>
                    <b-td>
                      <b-input-group append="EUR">
                        <b-form-input type="number" value="32"></b-form-input>
                      </b-input-group>
                    </b-td>
                    <b-td>
                      <b-input-group append="%">
                        <b-form-input type="number" value="43"></b-form-input>
                      </b-input-group>
                    </b-td>
                    <b-td>
                      <b-input-group append="EUR">
                        <b-form-input type="number" value="54"></b-form-input>
                      </b-input-group>
                    </b-td>
                    <b-td>
                      <b-input-group append="EUR">
                        <b-form-input type="number" value="65" disabled></b-form-input>
                      </b-input-group>
                    </b-td>
                    <b-td class="text-center">
                      <b-button-group>
                        <b-button size="sm" variant="info">
                          <i class="fa fa-fw fa-pencil-alt"></i>
                        </b-button>
                        <b-button size="sm" variant="danger">
                          <i class="fa fa-trash"></i>
                        </b-button>
                      </b-button-group>
                    </b-td>
                  </b-tr>
                </b-tbody>
              </b-table-simple>
              <b-table-simple responsive hover table-class="table-vcenter">
                <b-tbody>
                  <b-tr>
                    <b-td>
                      <h4>Einzelartikel</h4>
                    </b-td>
                  </b-tr>
                  <b-tr>
                    <b-td>
                      <h4>Dienstleistungen</h4>
                    </b-td>
                  </b-tr>
                  <b-tr>
                    <b-td>
                      <h4>Summe</h4>
                    </b-td>
                  </b-tr>
                  <b-tr>
                    <b-td class="text-right">
                      Gesamt netto (inkl. Rabatte, ohne optionale Positionen)
                    </b-td>
                    <b-td style="width: 15%;">
                      <b-input-group append="EUR">
                        <b-form-input type="number" value="32"></b-form-input>
                      </b-input-group>
                    </b-td>
                  </b-tr>
                  <b-tr>
                    <b-td class="text-right">
                      Umsatzsteuer
                    </b-td>
                    <b-td>
                      <b-input-group append="EUR">
                        <b-form-input type="number" value="32"></b-form-input>
                      </b-input-group>
                    </b-td>
                  </b-tr>
                  <b-tr>
                    <b-td class="text-right">
                      <b>Gesamt brutto</b>
                    </b-td>
                    <b-td>
                      <b-input-group append="EUR">
                        <b-form-input type="number" value="32"></b-form-input>
                      </b-input-group>
                    </b-td>
                  </b-tr>
                </b-tbody>
              </b-table-simple>
            </base-block>
          </b-col>
        </b-row>
        <h2>Montageleistungen</h2>
        <b-row class="push">
          <b-col>
            <base-block rounded>
              <b-table-simple responsive hover striped table-class="table-vcenter">
                <b-thead>
                  <b-tr>
                    <b-th>POSITION</b-th>
                    <b-th>Name</b-th>
                    <b-th>MENGE</b-th>
                    <b-th>PREIS PRO EINHEIT	</b-th>
                    <b-th>PREIS</b-th>
                    <b-th class="text-center" style="width: 100px;">Actions</b-th>
                  </b-tr>
                </b-thead>
                <b-tbody>
                  <b-tr v-for="user in users.slice(0, 6)" :key="user.id">
                    <b-td>
                      {{ user.id }}
                    </b-td>
                    <b-td class="font-w600 font-size-sm">
                      <b-form-input type="text" v-model="user.name"></b-form-input>
                    </b-td>
                    <b-td>
                      <b-input-group append="Stk">
                        <b-form-input type="text" value="s"></b-form-input>
                      </b-input-group>
                    </b-td>
                    <b-td>
                      <b-input-group append="EUR">
                        <b-form-input type="number" value="32"></b-form-input>
                      </b-input-group>
                    </b-td>
                    <b-td>
                      <b-input-group append="EUR">
                        <b-form-input type="number" value="32"></b-form-input>
                      </b-input-group>
                    </b-td>
                    <b-td class="text-center">
                      <b-button-group>
                        <b-button size="sm" variant="info">
                          <i class="fa fa-fw fa-pencil-alt"></i>
                        </b-button>
                        <b-button size="sm" variant="danger">
                          <i class="fa fa-trash"></i>
                        </b-button>
                      </b-button-group>
                    </b-td>
                  </b-tr>
                </b-tbody>
              </b-table-simple>
            </base-block>
          </b-col>
        </b-row>
        <h2>Fußzeile</h2>
        <b-row class="push">
          <b-col>
            <b-form-textarea id="example-textarea-input" rows="4" placeholder="Textarea content.."></b-form-textarea>
          </b-col>
        </b-row>
      </b-form>
      <h2>Konditionen</h2>
      <b-row class="push">
        <b-col lg="6">
          <b-form-group label="Lieferbedingungen" label-for="Lieferbedingungen">
            <b-form-select id="Lieferbedingungen" v-model="selected" :options="options" plain></b-form-select>
          </b-form-group>
          <b-form-group label="Zahlungsbedingungen" label-for="Zahlungsbedingungen">
            <b-form-select id="Zahlungsbedingungen" v-model="selected" :options="options" plain></b-form-select>
          </b-form-group>
            <b>Manuell geändert: <input type="checkbox"></b>
        </b-col>
      </b-row>
      <b-row class="push">
        <b-col offset-md="4">
          <b-button variant="info">Speichern</b-button>
          <b-button variant="info">Angebot versenden</b-button>
          <b-button variant="info">Auftrag Erstellen</b-button>
        </b-col>
      </b-row>
    </base-block>
    <!-- END Basic -->
  </div>
</template>

<style lang="scss" scoped>
// Custom backgrounds only for the hero of this page
.bg-landing-right {
  position: relative;
  z-index: 0;

  > div {
    z-index: 1;
  }

  &::before {
    position: absolute;
    z-index: 0;
    content: '';
  }
}

.bg-landing-right::before {
  bottom: -10%;
  right: -10%;
  width: 440px;
  height: 280px;
  background-image: url("data:image/svg+xml,%3Csvg width='64' height='64' viewBox='0 0 64 64' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M8 16c4.418 0 8-3.582 8-8s-3.582-8-8-8-8 3.582-8 8 3.582 8 8 8zm0-2c3.314 0 6-2.686 6-6s-2.686-6-6-6-6 2.686-6 6 2.686 6 6 6zm33.414-6l5.95-5.95L45.95.636 40 6.586 34.05.636 32.636 2.05 38.586 8l-5.95 5.95 1.414 1.414L40 9.414l5.95 5.95 1.414-1.414L41.414 8zM40 48c4.418 0 8-3.582 8-8s-3.582-8-8-8-8 3.582-8 8 3.582 8 8 8zm0-2c3.314 0 6-2.686 6-6s-2.686-6-6-6-6 2.686-6 6 2.686 6 6 6zM9.414 40l5.95-5.95-1.414-1.414L8 38.586l-5.95-5.95L.636 34.05 6.586 40l-5.95 5.95 1.414 1.414L8 41.414l5.95 5.95 1.414-1.414L9.414 40z' fill='%232C4E9B' fill-opacity='0.1' fill-rule='evenodd'/%3E%3C/svg%3E");
}

.promo-image {
  max-width: 100%;
  height: auto;
  border-radius: .375rem;
  box-shadow: 0 1rem 3rem rgba(108, 117, 125, .2);
}
</style>

<script>
export default {
  data () {
    return {
      selected: null,
      options: [
        { value: null, text: 'Please select' },
        { value: 1, text: 'Option #1' },
        { value: 2, text: 'Option #2' },
        { value: 3, text: 'Option #3' },
        { value: 4, text: 'Option #4' },
        { value: 5, text: 'Option #5' },
        { value: 6, text: 'Option #6' },
        { value: 7, text: 'Option #7' },
        { value: 8, text: 'Option #8' },
        { value: 9, text: 'Option #9' },
        { value: 10, text: 'Option #10' }
      ],
      selectedMultiple: [],
      optionsMultiple: [
        { value: 1, text: 'Option #1' },
        { value: 2, text: 'Option #2' },
        { value: 3, text: 'Option #3' },
        { value: 4, text: 'Option #4' },
        { value: 5, text: 'Option #5' },
        { value: 6, text: 'Option #6' },
        { value: 7, text: 'Option #7' },
        { value: 8, text: 'Option #8' },
        { value: 9, text: 'Option #9' },
        { value: 10, text: 'Option #10' }
      ],
      selectedCheckboxes: [],
      optionsCheckboxes: [
        { value: 1, text: 'Option 1' }
      ],
      selectedRadios: [],
      optionsRadios: [
        { value: 1, text: 'Option 1' },
        { value: 2, text: 'Option 2' },
        { value: 3, text: 'Option 3' }
      ],
      users: [
        {
          id: 1,
          name: 'Adam McCoy'
        },
        {
          id: 2,
          name: 'Betty Kelley'
        },
        {
          id: 3,
          name: 'Jesse Fisher'
        },
        {
          id: 4,
          name: 'Ryan Flores'
        },
        {
          id: 5,
          name: 'Alice Moore'
        },
        {
          id: 6,
          name: 'Scott Young'
        },
        {
          id: 7,
          name: 'Ralph Murray'
        },
        {
          id: 8,
          name: 'Marie Duncan'
        },
        {
          id: 9,
          name: 'Helen Jacobs'
        },
        {
          id: 10,
          name: 'Carl Wells'
        },
        {
          id: 11,
          name: 'Jose Mills'
        }
      ]
    }
  }
}
</script>
